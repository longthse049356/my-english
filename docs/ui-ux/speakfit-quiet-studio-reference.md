# SpeakFit Quiet Studio Reference Canvas Source

This is a frozen source reference copied from the live Cursor Canvas at:

`/Users/longth/.cursor/projects/Users-longth-My-English/canvases/speakfit-quiet-studio.canvas.tsx`

It is intentionally stored as Markdown so the app TypeScript compiler does not try to resolve the Canvas-only `cursor/canvas` module. AI agents should read this file as a UI/UX reference, not as production code.

This reference is intended to preserve the desired UI direction, color mood, visual hierarchy, layout shape, and interaction flow. It is **not** a pixel-perfect production sizing specification. Production implementation should adapt exact dimensions to the real web viewport while preserving the same perceived UI/UX.

```tsx
import { Button, Card, CardBody, CardHeader, Grid, H1, H2, H3, Pill, Row, Stack, Stat, Text, useCanvasState, useHostTheme } from 'cursor/canvas';

type PageId = 'onboarding' | 'today' | 'missions' | 'phrases' | 'progress' | 'settings' | 'operator';
type MissionStep = 'warmup' | 'shadow' | 'record' | 'feedback' | 'fallback' | 'complete';

const pages: Array<{ id: PageId; label: string; subtitle: string; group: 'learner' | 'internal' }> = [
  { id: 'onboarding', label: 'Onboarding', subtitle: 'First-run setup', group: 'learner' },
  { id: 'today', label: 'Today', subtitle: 'Daily mission', group: 'learner' },
  { id: 'missions', label: 'Missions', subtitle: 'Seeded scenarios', group: 'learner' },
  { id: 'phrases', label: 'Phrases', subtitle: 'Review & reuse', group: 'learner' },
  { id: 'progress', label: 'Progress', subtitle: 'Evidence & trend', group: 'learner' },
  { id: 'settings', label: 'Settings', subtitle: 'Profile & privacy', group: 'learner' },
  { id: 'operator', label: 'Operator', subtitle: 'Private testing', group: 'internal' },
];

const missionSteps: Array<{ id: MissionStep; label: string }> = [
  { id: 'warmup', label: 'Warm-up' },
  { id: 'shadow', label: 'Shadow' },
  { id: 'record', label: 'Record' },
  { id: 'feedback', label: 'Feedback' },
  { id: 'fallback', label: 'Fallback' },
  { id: 'complete', label: 'Complete' },
];

const waveform = [26, 42, 58, 34, 72, 46, 88, 54, 66, 38, 76, 48, 62, 30, 52, 40];

function SmallLabel({ children }: { children: string }) {
  const theme = useHostTheme();
  return (
    <Text size="small" weight="semibold" style={{ color: theme.text.tertiary, letterSpacing: '0.08em', textTransform: 'uppercase' }}>
      {children}
    </Text>
  );
}

function ProgressBar({ value }: { value: number }) {
  const theme = useHostTheme();
  return (
    <div style={{ height: 8, borderRadius: 999, background: theme.fill.tertiary, overflow: 'hidden' }}>
      <div style={{ width: `${value}%`, height: '100%', background: theme.accent.primary, borderRadius: 999 }} />
    </div>
  );
}

function VoiceWaveform() {
  const theme = useHostTheme();
  return (
    <Row gap={7} align="center" justify="center" style={{ height: 112 }}>
      {waveform.map((height, index) => (
        <div
          key={index}
          style={{
            width: 8,
            height,
            borderRadius: 999,
            background: index % 3 === 0 ? theme.accent.primary : theme.text.link,
            opacity: index < 3 || index > 13 ? 0.35 : 0.9,
          }}
        />
      ))}
    </Row>
  );
}

function AppSidebar({ activePage, setActivePage }: { activePage: PageId; setActivePage: (page: PageId) => void }) {
  const theme = useHostTheme();
  const learnerPages = pages.filter((page) => page.group === 'learner');
  const internalPages = pages.filter((page) => page.group === 'internal');

  return (
    <div style={{ borderRight: `1px solid ${theme.stroke.tertiary}`, padding: 16, minHeight: 820, background: theme.bg.chrome }}>
      <Stack gap={20}>
        <Stack gap={4}>
          <H2>SpeakFit</H2>
          <Text size="small" tone="secondary">Quiet Studio</Text>
        </Stack>

        <Stack gap={8}>
          {learnerPages.map((page) => <SidebarButton key={page.id} page={page} activePage={activePage} setActivePage={setActivePage} />)}
        </Stack>

        <Stack gap={8}>
          <SmallLabel>Internal</SmallLabel>
          {internalPages.map((page) => <SidebarButton key={page.id} page={page} activePage={activePage} setActivePage={setActivePage} />)}
        </Stack>

        <Card>
          <CardHeader trailing={<Pill tone="success" active size="sm">On</Pill>}>Safe practice</CardHeader>
          <CardBody>
            <Text size="small" tone="secondary">Private mode, fallback path, and data controls are part of the MVP trust layer.</Text>
          </CardBody>
        </Card>
      </Stack>
    </div>
  );
}

function SidebarButton({ page, activePage, setActivePage }: { page: { id: PageId; label: string; subtitle: string }; activePage: PageId; setActivePage: (page: PageId) => void }) {
  const theme = useHostTheme();
  const active = page.id === activePage;
  return (
    <button
      type="button"
      onClick={() => setActivePage(page.id)}
      style={{
        width: '100%',
        textAlign: 'left',
        border: `1px solid ${active ? theme.accent.primary : theme.stroke.tertiary}`,
        borderRadius: 14,
        padding: '11px 12px',
        background: active ? theme.fill.secondary : 'transparent',
        color: theme.text.primary,
        cursor: 'pointer',
      }}
    >
      <Stack gap={2}>
        <Text weight="semibold" as="span">{page.label}</Text>
        <Text size="small" tone="secondary" as="span">{page.subtitle}</Text>
      </Stack>
    </button>
  );
}

function TopNav({ activePage }: { activePage: PageId }) {
  const current = pages.find((page) => page.id === activePage) ?? pages[1];
  return (
    <Row justify="space-between" align="center" style={{ padding: '14px 20px' }}>
      <Stack gap={2}>
        <SmallLabel>{current.subtitle}</SmallLabel>
        <H1>{current.label}</H1>
      </Stack>
      <Row gap={8} align="center">
        <Pill active tone="info">Interview English</Pill>
        <Pill>B1 target</Pill>
        <Pill active tone="success">Private</Pill>
      </Row>
    </Row>
  );
}

function OnboardingPage({ setActivePage }: { setActivePage: (page: PageId) => void }) {
  return (
    <Grid columns="1.05fr 0.95fr" gap={18} align="start">
      <Stack gap={16}>
        <Text tone="secondary">Fast first-run setup. No heavy placement test — just enough context to generate the first useful mission.</Text>
        <Card size="lg">
          <CardHeader trailing={<Pill tone="info" active size="sm">Step 1</Pill>}>Practice profile</CardHeader>
          <CardBody>
            <Stack gap={18}>
              <Stack gap={8}>
                <SmallLabel>Main goal</SmallLabel>
                <Row gap={8} wrap><Pill active tone="info">Interview speaking</Pill><Pill>Workplace speaking</Pill></Row>
              </Stack>
              <Stack gap={8}>
                <SmallLabel>Self-rated level</SmallLabel>
                <Row gap={8} wrap><Pill>A2-high</Pill><Pill active tone="info">B1</Pill><Pill>B1+</Pill></Row>
              </Stack>
              <Stack gap={8}>
                <SmallLabel>Professional track</SmallLabel>
                <Row gap={8} wrap><Pill active tone="info">Software Engineer</Pill><Pill>Purchasing / Business</Pill><Pill>Garment industry</Pill></Row>
              </Stack>
              <Button variant="primary" onClick={() => setActivePage('today')}>Show my first mission</Button>
            </Stack>
          </CardBody>
        </Card>
      </Stack>
      <Card>
        <CardHeader>First mission preview</CardHeader>
        <CardBody>
          <Stack gap={12}>
            <H3>Introduce your recent project clearly</H3>
            <Text tone="secondary">A ready mission appears immediately after onboarding so the learner does not browse a course library or write their own prompt.</Text>
            <Row gap={8} wrap><Pill>5–10 min</Pill><Pill>Sample audio</Pill><Pill>One retry</Pill><Pill>Save phrase</Pill></Row>
          </Stack>
        </CardBody>
      </Card>
    </Grid>
  );
}

function MissionRail({ missionStep, setMissionStep }: { missionStep: MissionStep; setMissionStep: (step: MissionStep) => void }) {
  return (
    <Stack gap={14}>
      <Card>
        <CardHeader trailing={<Pill tone="info" active size="sm">Today</Pill>}>Mission</CardHeader>
        <CardBody>
          <Stack gap={14}>
            <Stack gap={6}>
              <SmallLabel>Interview English</SmallLabel>
              <H3>Introduce your recent project clearly</H3>
              <Text tone="secondary" size="small">Practice a 45-second answer for “Tell me about a project you worked on.”</Text>
            </Stack>
            <ProgressBar value={missionStep === 'complete' ? 100 : missionStep === 'feedback' ? 72 : 48} />
            <Grid columns={2} gap={10}><Stat value="12m" label="Estimated" /><Stat value="B1" label="Target" tone="info" /></Grid>
          </Stack>
        </CardBody>
      </Card>

      <Stack gap={8}>
        <SmallLabel>Mission loop</SmallLabel>
        {missionSteps.map((step) => <Pill key={step.id} active={missionStep === step.id} tone={missionStep === step.id ? 'info' : 'neutral'} onClick={() => setMissionStep(step.id)}>{step.label}</Pill>)}
      </Stack>

      <Card>
        <CardHeader>Useful opener</CardHeader>
        <CardBody>
          <Text weight="semibold">In my last project, I was responsible for…</Text>
          <Text tone="secondary" size="small">Use this to start with context before explaining results.</Text>
        </CardBody>
      </Card>
    </Stack>
  );
}

function RehearsalStage({ missionStep, setMissionStep }: { missionStep: MissionStep; setMissionStep: (step: MissionStep) => void }) {
  const theme = useHostTheme();
  const isRecord = missionStep === 'record';
  const title = missionStep === 'warmup' ? 'Listen first, then notice the answer structure.' : missionStep === 'shadow' ? 'Shadow the sample in small speakable chunks.' : missionStep === 'fallback' ? 'Mic blocked? Keep the mission moving with text.' : 'Tell me about a project you worked on and what result you created.';

  return (
    <Stack gap={16}>
      <div style={{ borderRadius: 24, background: theme.bg.elevated, border: `1px solid ${theme.stroke.secondary}`, padding: 26 }}>
        <Stack gap={20}>
          <Row justify="space-between" align="center">
            <Pill tone={missionStep === 'fallback' ? 'warning' : 'info'} active>{missionStep === 'fallback' ? 'Recovery path' : 'Private voice studio'}</Pill>
            <Text size="small" tone="secondary">{isRecord ? '00:28 / 00:45' : '5–10 min session'}</Text>
          </Row>

          <Stack gap={10}>
            <SmallLabel>{missionStep === 'fallback' ? 'Manual transcript fallback' : 'Speaking prompt'}</SmallLabel>
            <H2 style={{ maxWidth: 720 }}>{title}</H2>
            <Row gap={8} wrap>
              <Pill active={missionStep === 'warmup'} tone="info">Sample answer</Pill>
              <Pill active={missionStep === 'shadow'} tone="info">Phrase chunks</Pill>
              <Pill active={missionStep === 'record'} tone="info">Record answer</Pill>
              <Pill active={missionStep === 'feedback'} tone="info">Coach feedback</Pill>
            </Row>
          </Stack>

          {missionStep === 'warmup' && <SampleAnswer />}
          {missionStep === 'shadow' && <ShadowChunks />}
          {missionStep === 'fallback' && <FallbackBox />}
          {(missionStep === 'record' || missionStep === 'feedback' || missionStep === 'complete') && <VoiceWaveform />}

          <Row gap={12} align="center" justify="center">
            {missionStep === 'warmup' && <Button variant="primary" onClick={() => setMissionStep('shadow')}>Practice chunks</Button>}
            {missionStep === 'shadow' && <Button variant="primary" onClick={() => setMissionStep('record')}>Record answer</Button>}
            {missionStep === 'record' && <Button variant="primary" onClick={() => setMissionStep('feedback')}>Stop and get feedback</Button>}
            {missionStep === 'feedback' && <Button variant="primary" onClick={() => setMissionStep('complete')}>Complete with retry</Button>}
            {missionStep === 'fallback' && <Button variant="primary" onClick={() => setMissionStep('feedback')}>Submit text answer</Button>}
            {missionStep === 'complete' && <Button variant="primary">Save mission</Button>}
            <Button variant="secondary" onClick={() => setMissionStep('fallback')}>Mic not working?</Button>
          </Row>

          <Text tone="secondary" size="small" style={{ textAlign: 'center' }}>Private practice. Retry before finishing. Structure matters more than perfection.</Text>
        </Stack>
      </div>

      <Card>
        <CardHeader trailing={missionStep === 'fallback' ? 'Manual input' : 'Draft transcript'}>Answer area</CardHeader>
        <CardBody>
          <Text>I worked on an onboarding checklist for new team members. My role was to collect common questions and turn them into a simple guide. After that, new members could start faster...</Text>
        </CardBody>
      </Card>
    </Stack>
  );
}

function SampleAnswer() {
  return (
    <Card>
      <CardHeader trailing={<Pill size="sm">Sample audio</Pill>}>Warm-up sample</CardHeader>
      <CardBody>
        <Stack gap={10}>
          <Text>I worked on an onboarding checklist for new team members. I collected common questions, organized them into clear steps, and helped the team reduce repeated explanations.</Text>
          <Row gap={8}><Button variant="secondary">Play sample</Button><Button variant="ghost">Replay sentence</Button></Row>
        </Stack>
      </CardBody>
    </Card>
  );
}

function ShadowChunks() {
  return (
    <Stack gap={10}>
      <Row gap={8} wrap><Pill active tone="info">I worked on…</Pill><Pill>My role was…</Pill><Pill>The result was…</Pill></Row>
      <Text tone="secondary" size="small">Repeat each chunk once before recording your own answer.</Text>
    </Stack>
  );
}

function FallbackBox() {
  return (
    <Card>
      <CardHeader trailing={<Pill tone="warning" active size="sm">Recoverable</Pill>}>Voice pipeline issue</CardHeader>
      <CardBody>
        <Stack gap={10}>
          <Text>Your microphone or STT can fail without losing the session. Type or paste your answer and continue to the same feedback and retry loop.</Text>
          <Row gap={8}><Button variant="secondary">Try permission again</Button><Button variant="ghost">Use text answer</Button></Row>
        </Stack>
      </CardBody>
    </Card>
  );
}

function CoachPanel({ missionStep, setMissionStep }: { missionStep: MissionStep; setMissionStep: (step: MissionStep) => void }) {
  return (
    <Stack gap={14}>
      <Card>
        <CardHeader trailing={<Pill tone={missionStep === 'feedback' || missionStep === 'complete' ? 'success' : 'neutral'} active={missionStep === 'feedback' || missionStep === 'complete'} size="sm">{missionStep === 'feedback' || missionStep === 'complete' ? 'Ready' : 'Locked'}</Pill>}>Coach feedback</CardHeader>
        <CardBody>
          <Stack gap={14}>
            <Stack gap={4}><SmallLabel>What worked</SmallLabel><Text size="small">Good start — your answer has a clear direction.</Text></Stack>
            <Stack gap={4}><SmallLabel>Fix one thing</SmallLabel><Text size="small">Make the project result more specific and measurable.</Text></Stack>
            <Stack gap={6}>
              <SmallLabel>Better phrase</SmallLabel>
              <Text size="small" weight="semibold">I helped reduce onboarding time by creating a checklist for new team members.</Text>
              <Row gap={8}><Button variant="secondary">Save phrase</Button><Button variant="ghost">Use in retry</Button></Row>
            </Stack>
          </Stack>
        </CardBody>
      </Card>

      <div style={{ padding: 16 }}>
        <Stack gap={10}>
          <SmallLabel>Retry focus</SmallLabel>
          <H3>This time: add one specific project result.</H3>
          <Button variant="primary" onClick={() => setMissionStep('record')}>Retry with coach tip</Button>
        </Stack>
      </div>

      {missionStep === 'complete' && <QuietGift />}
    </Stack>
  );
}

function QuietGift() {
  return (
    <Card>
      <CardHeader trailing={<Pill tone="success" active size="sm">Optional</Pill>}>Coach note</CardHeader>
      <CardBody>
        <Stack gap={10}>
          <Text weight="semibold">You showed up and retried. That is the habit that improves speaking.</Text>
          <Row gap={8}><Button variant="secondary">Save note</Button><Button variant="ghost">Dismiss</Button></Row>
        </Stack>
      </CardBody>
    </Card>
  );
}

function TodayPage() {
  const [missionStep, setMissionStep] = useCanvasState<MissionStep>('mission-step', 'warmup');
  return (
    <Stack gap={18}>
      <Text tone="secondary">One mission. Warm up, shadow, speak, receive one practical improvement, retry, then save one useful phrase.</Text>
      <Grid columns="280px minmax(520px, 1fr) 340px" gap={20} align="start">
        <MissionRail missionStep={missionStep} setMissionStep={setMissionStep} />
        <RehearsalStage missionStep={missionStep} setMissionStep={setMissionStep} />
        <CoachPanel missionStep={missionStep} setMissionStep={setMissionStep} />
      </Grid>
    </Stack>
  );
}

function MissionsPage() {
  return (
    <Stack gap={18}>
      <Row justify="space-between" align="center">
        <Text tone="secondary">A small seeded mission set for MVP testing — not a broad course library.</Text>
        <Button variant="primary">Start selected mission</Button>
      </Row>
      <Grid columns={3} gap={14}>
        {[
          ['Interview intro', 'Tell me about yourself with a clear professional arc.', '8 min', 'Interview'],
          ['Recent project', 'Explain responsibility, action, and measurable result.', '12 min', 'Interview'],
          ['Standup update', 'Share progress, blocker, and next action concisely.', '6 min', 'Workplace'],
          ['Ask for clarification', 'Request detail without sounding unsure.', '5 min', 'Meetings'],
          ['Supplier delay', 'Explain a timeline issue calmly and professionally.', '10 min', 'Business'],
          ['Shadowing drill', 'Repeat natural rhythm for common work phrases.', '7 min', 'Shadowing'],
        ].map(([title, description, duration, tag]) => (
          <Card key={title}>
            <CardHeader trailing={<Pill size="sm">{tag}</Pill>}>{title}</CardHeader>
            <CardBody>
              <Stack gap={12}>
                <Text size="small" tone="secondary">{description}</Text>
                <Row justify="space-between" align="center"><Text size="small" tone="tertiary">{duration}</Text><Button variant="secondary">Preview</Button></Row>
              </Stack>
            </CardBody>
          </Card>
        ))}
      </Grid>
    </Stack>
  );
}

function PhrasesPage() {
  return (
    <Stack gap={18}>
      <Grid columns="1.2fr 0.8fr" gap={16}>
        <Card size="lg">
          <CardHeader trailing={<Pill tone="info" active size="sm">24 saved</Pill>}>Saved phrase review</CardHeader>
          <CardBody>
            <Stack gap={12}>
              {[
                ['In my last project, I was responsible for…', 'Recent project mission', 'Reviewed'],
                ['The result was a clearer process for new team members.', 'Coach feedback', 'Use in retry'],
                ['One challenge was that we needed to align quickly.', 'Standup update', 'New'],
                ['Could you clarify the priority for this week?', 'Meeting scenario', 'Reused'],
              ].map(([phrase, context, status]) => (
                <div key={phrase} style={{ padding: 12 }}>
                  <Stack gap={6}>
                    <Text weight="semibold">{phrase}</Text>
                    <Row justify="space-between" align="center"><Text size="small" tone="secondary">Original context: {context}</Text><Pill tone={status === 'Reused' ? 'success' : status === 'New' ? 'warning' : 'info'} active size="sm">{status}</Pill></Row>
                    <Row gap={8}><Button variant="secondary">Practice with this</Button><Button variant="ghost">Mark reused</Button></Row>
                  </Stack>
                </div>
              ))}
            </Stack>
          </CardBody>
        </Card>
        <Stack gap={14}>
          <H2>Personal speaking toolbox</H2>
          <Text tone="secondary">Saved language should re-enter future speaking attempts, not become dead bookmarks.</Text>
          <Row gap={8} wrap><Pill active tone="info">Opening</Pill><Pill>Project result</Pill><Pill>Strength</Pill><Pill>Challenge</Pill><Pill>Clarifying</Pill></Row>
          <Card><CardHeader>Review target</CardHeader><CardBody><Text>Review or reuse at least 2 saved phrases this week.</Text></CardBody></Card>
        </Stack>
      </Grid>
    </Stack>
  );
}

function ProgressPage() {
  return (
    <Stack gap={18}>
      <Grid columns={4} gap={12}><Stat value="7" label="Missions completed" tone="success" /><Stat value="18" label="Attempts made" /><Stat value="11" label="Retries completed" tone="info" /><Stat value="6" label="Phrases reused" /></Grid>
      <Grid columns="1.1fr 0.9fr" gap={16}>
        <Card size="lg">
          <CardHeader>7-day confidence trend</CardHeader>
          <CardBody>
            <Stack gap={14}>
              {[["Mon", 2], ["Tue", 2], ["Wed", 3], ["Thu", 3], ["Fri", 4]].map(([day, value]) => (
                <Stack key={day} gap={6}><Row justify="space-between"><Text size="small">{day}</Text><Text size="small" tone="secondary">{value}/5 after practice</Text></Row><ProgressBar value={Number(value) * 20} /></Stack>
              ))}
            </Stack>
          </CardBody>
        </Card>
        <Card>
          <CardHeader>Before / after evidence</CardHeader>
          <CardBody>
            <Stack gap={12}>
              <Row justify="space-between"><Text tone="secondary">Attempt 1</Text><Button variant="secondary">Replay</Button></Row>
              <Row justify="space-between"><Text tone="secondary">Retry</Text><Button variant="secondary">Replay</Button></Row>
              <Text weight="semibold">Improved: added a measurable project result.</Text>
            </Stack>
          </CardBody>
        </Card>
      </Grid>
      <Card><CardHeader>Common retry focus</CardHeader><CardBody><Row gap={8} wrap><Pill active tone="warning">Add specific result</Pill><Pill>Shorter opening</Pill><Pill>Clearer responsibility</Pill><Pill>More natural rhythm</Pill></Row></CardBody></Card>
    </Stack>
  );
}

function SettingsPage() {
  return (
    <Stack gap={18}>
      <Grid columns="1fr 1fr" gap={16}>
        <Card><CardHeader>Practice profile</CardHeader><CardBody><Stack gap={12}><Row justify="space-between"><Text tone="secondary">Target role</Text><Text weight="semibold">Software Engineer</Text></Row><Row justify="space-between"><Text tone="secondary">English level</Text><Text weight="semibold">B1</Text></Row><Row justify="space-between"><Text tone="secondary">Main goal</Text><Text weight="semibold">Interview confidence</Text></Row></Stack></CardBody></Card>
        <Card><CardHeader>Privacy and language</CardHeader><CardBody><Stack gap={12}><Row justify="space-between"><Text tone="secondary">Private mode</Text><Pill active tone="success">On</Pill></Row><Row justify="space-between"><Text tone="secondary">Feedback language</Text><Pill>English + Vietnamese</Pill></Row><Row justify="space-between"><Text tone="secondary">Save recordings</Text><Pill>Ask every time</Pill></Row></Stack></CardBody></Card>
      </Grid>
      <Grid columns="1fr 1fr" gap={16}>
        <Card><CardHeader>Data control</CardHeader><CardBody><Stack gap={10}><Text>Recordings, transcripts, feedback, and saved phrases are sensitive learner data.</Text><Row gap={8}><Button variant="secondary">Delete practice artifacts</Button><Button variant="ghost">Export phrases</Button></Row></Stack></CardBody></Card>
        <Card><CardHeader>Provider notice</CardHeader><CardBody><Text>Audio or transcripts may be sent to AI/STT/TTS providers when needed. AI feedback is coaching guidance, not certification or hiring evaluation.</Text></CardBody></Card>
      </Grid>
    </Stack>
  );
}

function OperatorPage() {
  return (
    <Stack gap={18}>
      <Text tone="secondary">Internal/private testing view for Solo PM. Kept outside learner navigation scope in production.</Text>
      <Grid columns={4} gap={12}><Stat value="12" label="Mission templates" /><Stat value="$8.40" label="AI/TTS/STT today" tone="warning" /><Stat value="73%" label="Retry rate" tone="success" /><Stat value="42" label="Saved phrases" /></Grid>
      <Grid columns="1fr 1fr" gap={16}>
        <Card><CardHeader>Mission template queue</CardHeader><CardBody><Stack gap={10}><Row justify="space-between"><Text>Recent project answer</Text><Pill active tone="success">Verified</Pill></Row><Row justify="space-between"><Text>Supplier delay update</Text><Pill tone="warning" active>Needs review</Pill></Row><Row justify="space-between"><Text>Clarify meeting priority</Text><Pill>Draft</Pill></Row></Stack></CardBody></Card>
        <Card><CardHeader>Cost and provider guardrail</CardHeader><CardBody><Stack gap={12}><ProgressBar value={42} /><Text tone="secondary">Daily spend threshold: 42% used. Surface alerts before dogfood costs spike.</Text><Row gap={8}><Button variant="secondary">View usage</Button><Button variant="ghost">Pause STT</Button></Row></Stack></CardBody></Card>
      </Grid>
    </Stack>
  );
}

function PageContent({ activePage, setActivePage }: { activePage: PageId; setActivePage: (page: PageId) => void }) {
  if (activePage === 'onboarding') return <OnboardingPage setActivePage={setActivePage} />;
  if (activePage === 'missions') return <MissionsPage />;
  if (activePage === 'phrases') return <PhrasesPage />;
  if (activePage === 'progress') return <ProgressPage />;
  if (activePage === 'settings') return <SettingsPage />;
  if (activePage === 'operator') return <OperatorPage />;
  return <TodayPage />;
}

export default function SpeakFitQuietStudioPreview() {
  const theme = useHostTheme();
  const [activePage, setActivePage] = useCanvasState<PageId>('active-page', 'today');

  return (
    <div style={{ border: `1px solid ${theme.stroke.tertiary}`, borderRadius: 20, overflow: 'hidden', background: theme.bg.editor }}>
      <Grid columns="232px minmax(0, 1fr)" gap={0} align="stretch">
        <AppSidebar activePage={activePage} setActivePage={setActivePage} />
        <Stack gap={0}>
          <TopNav activePage={activePage} />
          <div style={{ borderTop: `1px solid ${theme.stroke.tertiary}`, padding: 20, background: theme.bg.editor }}>
            <PageContent activePage={activePage} setActivePage={setActivePage} />
          </div>
        </Stack>
      </Grid>
    </div>
  );
}
```

## Required UI/UX structure captured by the source

- Compact app shell: left sidebar plus top nav.
- Learner pages: `Onboarding`, `Today`, `Missions`, `Phrases`, `Progress`, `Settings`.
- Internal page: `Operator` for Solo PM/private testing only.
- `Today` page: three-area workspace with mission rail, central rehearsal stage, coach panel.
- Mission states: `Warm-up`, `Shadow`, `Record`, `Feedback`, `Fallback`, `Complete`.
- MVP trust layer: private practice, manual text fallback, provider notice, delete/export controls.
- Learning asset loop: save phrase, use in retry, review/reuse saved phrases with original context.
- Progress evidence: confidence 1–5, attempts, retries, reused phrases, before/after replay evidence.

## Production fidelity guidance

Preserve the UI direction, color mood, layout shape, hierarchy, and interaction flow. Do not treat the Canvas preview dimensions as mandatory production dimensions. When implementing with `shadcn/ui` and Tailwind, follow `docs/ui-ux/shadcn-tailwind-implementation-contract.md` as the production bridge.

## Related

- [[shadcn-tailwind-implementation-contract|Shadcn/Tailwind Implementation Contract]] — production mapping.
- [[DESIGN|DESIGN — Quiet Studio]] — design thesis.
- [[ux-design-specification|UX Design Specification]] — UX flows & states.
- [[prd|PRD]] — MVP scope reference.
- [[product-brief|Product Brief]] — Discovery boundary.
- [[architecture|Architecture]] — frontend architecture.
- [[docs/ui-ux/README|UI/UX README]] — folder entry point.
- [[docs/INDEX|Repo Index]].
