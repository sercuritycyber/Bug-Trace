# Contributing to BugTrace

Thanks for your interest in contributing! Here's how to get involved.

## Reporting Bugs

Open an issue and include:
- Your OS and version
- Steps to reproduce
- What you expected vs what happened
- Any error messages from the console (View → Toggle DevTools)

## Suggesting Tools or Features

Open an issue with the label `enhancement`. Describe:
- What the tool/feature would do
- Which stage of bug hunting it helps with (recon, analysis, reporting, etc.)

## Submitting a Pull Request

1. Fork the repo and create a branch: `git checkout -b feature/my-tool`
2. Make your changes in `src/App.jsx`
3. Test with `npm run dev`
4. Keep new tools consistent with the existing style (same CSS tokens, same card/finding structure)
5. Open a PR with a clear description of what was added and why

## Adding a New Tool

Each tool is a self-contained React function component. Follow this pattern:

```jsx
function MyTool() {
  const [input, setInput] = useState("");
  const [output, setOutput] = useState("");

  function run() {
    // your logic here
    setOutput("result");
  }

  return (
    <div>
      <div className="card">
        <div className="card-title">My Tool</div>
        <textarea value={input} onChange={e => setInput(e.target.value)} rows={6} />
        <button className="btn btn-primary" onClick={run}>Run</button>
      </div>
      {output && <div className="card"><CopyBlock content={output} /></div>}
    </div>
  );
}
```

Then register it in the `TOOLS`, `TITLES`, `SUBS`, and `RENDER` config objects at the bottom of `App.jsx`.

## Code Style

- Keep it minimal — no external dependencies beyond React
- Use the existing `C` colour tokens for any new styles
- All logic should run fully offline (no API calls)
