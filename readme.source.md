```aura width=410 height=210 inline align=center
(function() {
  var stars = (github && github.stats && github.stats.totalStars) || 0;
  var commits = (github && github.stats && github.stats.totalCommits) || 0;
  var repos = (github && github.stats && github.stats.totalRepos) || 0;
  var forks = (github && github.stats && github.stats.totalForks) || 0;

  var items = [
    { label: 'Total Commits', value: commits, color: '#f59e0b' },
    { label: 'Total Stars', value: stars, color: '#60a5fa' },
    { label: 'Total Repos', value: repos, color: '#a78bfa' },
    { label: 'Total Forks', value: forks, color: '#34d399' },
  ];

  return (
    <div style={{
      width: '100%', height: '100%',
      background: '#08080c',
      display: 'flex', flexDirection: 'column',
      justifyContent: 'center', padding: '24px 28px',
      fontFamily: 'Inter, sans-serif', borderRadius: 16,
      border: '1px solid rgba(110,80,220,0.22)',
      position: 'relative', overflow: 'hidden',
    }}>
      <style>{`
        @keyframes orb1 { 0%, 100% { transform: translateX(0px); opacity: 0.7; } 50% { transform: translateX(120px); opacity: 1; } }
        @keyframes orb2 { 0%, 100% { transform: translateX(0px); opacity: 0.6; } 50% { transform: translateX(-100px); opacity: 0.9; } }
        #s-orb1 { animation: orb1 8s ease-in-out infinite; }
        #s-orb2 { animation: orb2 10s ease-in-out infinite; }
      `}</style>
      <svg width="410" height="210" style={{ position: 'absolute', top: 0, left: 0 }}>
        <defs>
          <radialGradient id="sg1" cx="50%" cy="50%" r="50%">
            <stop offset="0%" stopColor="rgba(115,20,215,0.65)" />
            <stop offset="70%" stopColor="rgba(85,15,175,0)" />
          </radialGradient>
          <radialGradient id="sg2" cx="50%" cy="50%" r="50%">
            <stop offset="0%" stopColor="rgba(55,55,255,0.5)" />
            <stop offset="70%" stopColor="rgba(35,45,210,0)" />
          </radialGradient>
        </defs>
        <ellipse id="s-orb1" cx="120" cy="180" rx="180" ry="120" fill="url(#sg1)" />
        <ellipse id="s-orb2" cx="300" cy="190" rx="160" ry="110" fill="url(#sg2)" />
      </svg>
      <div style={{ display: 'flex', fontSize: 11, fontWeight: 700, color: 'rgba(167,139,250,0.85)', letterSpacing: '2px', marginBottom: 16, textTransform: 'uppercase' }}>
        GitHub Stats
      </div>
      <div style={{ display: 'flex', flexDirection: 'column', gap: 10 }}>
        {items.map(function(item) {
          return (
            <div key={item.label} style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center' }}>
              <span style={{ fontSize: 13, color: 'rgba(255,255,255,0.7)', fontWeight: 500 }}>{item.label}:</span>
              <span style={{ fontSize: 14, fontWeight: 700, color: item.color }}>{item.value}</span>
            </div>
          );
        })}
      </div>
    </div>
  );
})()
```

```aura width=410 height=210 inline align=center
(function() {
  var langs = (github && github.languages && github.languages.length > 0)
    ? github.languages.slice(0, 5)
    : [
        { name: 'TypeScript', percentage: 48, color: '#3178c6' },
        { name: 'JavaScript', percentage: 28, color: '#f1e05a' },
        { name: 'HTML', percentage: 14, color: '#e34c26' },
        { name: 'CSS', percentage: 10, color: '#563d7c' },
      ];

  return (
    <div style={{
      width: '100%', height: '100%',
      background: '#08080c',
      display: 'flex', flexDirection: 'column',
      justifyContent: 'center', padding: '24px 28px',
      fontFamily: 'Inter, sans-serif', borderRadius: 16,
      border: '1px solid rgba(110,80,220,0.22)',
      position: 'relative', overflow: 'hidden',
    }}>
      <style>{`
        @keyframes l-orb1 { 0%, 100% { transform: translateX(0px); opacity: 0.6; } 50% { transform: translateX(-110px); opacity: 0.95; } }
        @keyframes l-orb2 { 0%, 100% { transform: translateX(0px); opacity: 0.55; } 50% { transform: translateX(90px); opacity: 0.85; } }
        #lg-orb1 { animation: l-orb1 9s ease-in-out infinite; }
        #lg-orb2 { animation: l-orb2 11s ease-in-out infinite; }
      `}</style>
      <svg width="410" height="210" style={{ position: 'absolute', top: 0, left: 0 }}>
        <defs>
          <radialGradient id="lg1" cx="50%" cy="50%" r="50%">
            <stop offset="0%" stopColor="rgba(40,60,255,0.6)" />
            <stop offset="70%" stopColor="rgba(30,50,200,0)" />
          </radialGradient>
          <radialGradient id="lg2" cx="50%" cy="50%" r="50%">
            <stop offset="0%" stopColor="rgba(110,20,210,0.55)" />
            <stop offset="70%" stopColor="rgba(90,15,180,0)" />
          </radialGradient>
        </defs>
        <ellipse id="lg-orb1" cx="280" cy="180" rx="170" ry="120" fill="url(#lg1)" />
        <ellipse id="lg-orb2" cx="120" cy="190" rx="160" ry="110" fill="url(#lg2)" />
      </svg>
      <div style={{ display: 'flex', fontSize: 11, fontWeight: 700, color: 'rgba(96,165,250,0.9)', letterSpacing: '2px', marginBottom: 12, textTransform: 'uppercase' }}>
        Top Languages
      </div>

      <div style={{ display: 'flex', width: '100%', height: 6, borderRadius: 3, overflow: 'hidden', marginBottom: 14, background: 'rgba(255,255,255,0.06)' }}>
        {langs.map(function(l) {
          return (
            <div key={l.name} style={{ width: l.percentage + '%', height: '100%', background: l.color }} />
          );
        })}
      </div>

      <div style={{ display: 'flex', flexDirection: 'column', gap: 6 }}>
        {langs.map(function(l) {
          return (
            <div key={l.name} style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center' }}>
              <div style={{ display: 'flex', alignItems: 'center', gap: 8 }}>
                <div style={{ width: 8, height: 8, borderRadius: 4, background: l.color }} />
                <span style={{ fontSize: 12, color: 'rgba(255,255,255,0.8)', fontWeight: 500 }}>{l.name}</span>
              </div>
              <span style={{ fontSize: 12, fontWeight: 600, color: 'rgba(255,255,255,0.5)' }}>{l.percentage}%</span>
            </div>
          );
        })}
      </div>
    </div>
  );
})()
```
