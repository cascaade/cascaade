# Cursed Code Hall of Fame

i start this today to document some of the worst code i've ever written.

### 01. A settings dialog

```tsx
<div className={styles.settingsContent}>
    {
        settings.find(tab => tab.id === selectedSettingsTab).settings.map((group, gi) => (
            <div className={styles.settingGroup} key={gi}>
                {
                    group.map((setting, i) => {
                        if (typeof(setting) === "string") {
                            return (<div key={i} className={styles.settingGroupTitle}>
                                { setting }
                            </div>)
                        } else {
                            return (<div key={i} className={styles.settingContainer}>
                                <div className={styles.settingLabel}>{setting.label}</div>
                                {(() => {
                                    switch (setting.type) {
                                        case "text":
                                            return (<input type="text"/>)
                                        case "password":
                                            return (<input type="password"/>)
                                    }
                                })()}
                            </div>)
                        }
                    })
                }
            </div>
        ))
    }
</div>
```
