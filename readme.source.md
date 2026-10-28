```aura width=860 height=140
(function() {
  var stats = [
    { label: 'REPOS', value: String((github && github.stats && github.stats.totalRepos) || 0), color: '#a78bfa' },
    { label: 'STARS', value: String((github && github.stats && github.stats.totalStars) || 0), color: '#60a5fa' },
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
