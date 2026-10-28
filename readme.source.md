```aura width=860 height=140
(function() {
  var stats = [
    { label: 'REPOS', value: String((github && github.stats && github.stats.totalRepos) || 0), color: '#a78bfa' },
    { label: 'STARS', value: String((github && github.stats && github.stats.totalStars) || 0)```aura width=410 height=210 inline align=center
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

      {/* Barra de progresso multi-colorida */}
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
```, color: '#60a5fa' },
    { label: 'COMMITS', value: String((github && github.stats && github.stats.totalCommits) || 0), color: '#f59e0b' },
  ];

  return (
    <div style={{
      width: '100%', height: '100%',
      background: '#08080c',
      display: 'flex', alignItems: 'center', justifyContent: 'center',
      fontFamily: 'Inter', borderRadius: 16,
      border: '1px solid rgba(110,80,220,0.18)',
      position: 'relative', overflow: 'hidden',
    }}>
      <style>
        {`
          @keyframes float-slow {
            0%, 100% { transform: translateX(0px); opacity: 0.8; }
            50% { transform: translateX(350px); opacity: 1.2; }
          }
          @keyframes float-medium {
            0%, 100% { transform: translateX(0px); opacity: 0.7; }
            50% { transform: translateX(-250px); opacity: 1.1; }
          }
          #glow-1 { animation: float-slow 9s ease-in-out infinite; }
          #glow-2 { animation: float-medium 12s ease-in-out infinite; }
        `}
      </style>

      <svg width="860" height="140" style={{ position: 'absolute', top: 0, left: 0 }}>
        <defs>
          <radialGradient id="g1" cx="50%" cy="50%" r="50%">
            <stop offset="0%" stopColor="rgba(115,20,215,0.68)" />
            <stop offset="70%" stopColor="rgba(85,15,175,0)" />
          </radialGradient>
          <radialGradient id="g2" cx="50%" cy="50%" r="50%">
            <stop offset="0%" stopColor="rgba(55,55,255,0.55)" />
            <stop offset="70%" stopColor="rgba(35,45,210,0)" />
          </radialGradient>
        </defs>
        <ellipse id="glow-1" cx="200" cy="140" rx="250" ry="160" fill="url(#g1)" />
        <ellipse id="glow-2" cx="600" cy="140" rx="220" ry="140" fill="url(#g2)" />
      </svg>

      <div style={{ display: 'flex', width: '100%', justifyContent: 'space-around', padding: '0 40px', zIndex: 1 }}>
        {stats.map(function(s, idx) {
          return (
            <div key={s.label} style={{ display: 'flex', flexDirection: 'column', alignItems: 'center', flex: 1, borderRight: idx < stats.length - 1 ? '1px solid rgba(255,255,255,0.06)' : 'none' }}>
              <span style={{ fontSize: 36, fontWeight: 800, color: s.color, letterSpacing: '-1px' }}>{s.value}</span>
              <span style={{ fontSize: 11, fontWeight: 700, color: 'rgba(255,255,255,0.4)', letterSpacing: '2px', marginTop: 4 }}>{s.label}</span>
            </div>
          );
        })}
      </div>
    </div>
  );
})()
```

<br>

```aura width=860 height=168
(function() {
  var categories = [
    { title: 'LANGUAGES', color: '#a78bfa', items: ['TypeScript', 'JavaScript', 'C++'] },
    { title: 'FRAMEWORKS', color: '#38bdf8', items: ['React Native', 'React', 'Next.js'] },
  ];

  return (
    <div style={{
      width: '100%', height: '100%', background: '#08080c',
      display: 'flex', flexDirection: 'column', justifyContent: 'center', padding: '0 40px', gap: 14,
      fontFamily: 'Inter', borderRadius: 16, border: '1px solid rgba(110,80,220,0.18)',
      position: 'relative', overflow: 'hidden'
    }}>
      <style>
        {`
          @keyframes float-tech {
            0%, 100% { transform: translateX(0px); opacity: 0.7; }
            50% { transform: translateX(250px); opacity: 1.0; }
          }
          #glow-tech { animation: float-tech 10s ease-in-out infinite; }
        `}
      </style>
      <svg width="860" height="168" style={{ position: 'absolute', top: 0, left: 0 }}>
        <defs>
          <radialGradient id="gt" cx="50%" cy="50%" r="50%">
            <stop offset="0%" stopColor="rgba(110,20,210,0.6)" />
            <stop offset="70%" stopColor="rgba(90,15,180,0)" />
          </radialGradient>
        </defs>
        <ellipse id="glow-tech" cx="400" cy="168" rx="280" ry="150" fill="url(#gt)" />
      </svg>

      <div style={{ display: 'flex', fontSize: 10, fontWeight: 700, color: 'rgba(155,140,210,0.6)', letterSpacing: '3px' }}>
        TECH STACK
      </div>
      <div style={{ display: 'flex', flexDirection: 'column', gap: 12 }}>
        {categories.map(function(cat) {
          return (
            <div key={cat.title} style={{ display: 'flex', alignItems: 'center', gap: 16 }}>
              <div style={{ display: 'flex', fontSize: 10, fontWeight: 700, color: cat.color, letterSpacing: '1px', width: 90 }}>
                {cat.title}
              </div>
              <div style={{ display: 'flex', flexWrap: 'wrap', gap: 8 }}>
                {cat.items.map(function(item) {
                  return (
                    <div key={item} style={{
                      display: 'flex', padding: '4px 13px', borderRadius: 6,
                      background: cat.color + '15', border: '1px solid ' + cat.color + '35',
                      color: 'rgba(225,220,255,0.85)', fontSize: 12, fontWeight: 600,
                    }}>{item}</div>
                  );
                })}
              </div>
            </div>
          );
        })}
      </div>
    </div>
  );
})()
```

<br>

```aura width=130 height=44 link="https://linkedin.com/in/SEU_LINKEDIN" inline align=center
<SocialMediaButton
  icon="https://cdn.simpleicons.org/linkedin/0A66C2"
  text="Linkedin"
  backgroundColor="#0c182b"
  width={130}
  height={44}
/>
```

```aura width=120 height=44 link="https://x.com/SEU_USER" inline align=center
<SocialMediaButton
  icon="https://cdn.simpleicons.org/x/ffffff"
  text="X.com"
  backgroundColor="#141414"
  width={120}
  height={44}
/>
```

```aura width=120 height=44 link="mailto:seu-email@gmail.com" inline align=center
<SocialMediaButton
  icon="https://cdn.simpleicons.org/gmail/EA4335"
  text="Email"
  backgroundColor="#2b0a0a"
  width={120}
  height={44}
/>
```

<br>
<p align="center"><sub>powered by <a href="https://github.com/collectioneur/readme-aura">readme-aura</a></sub></p>
