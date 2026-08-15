# GPO - Conrol Panel Restriciton (LAB-Users)

**Issue / Symptom:** An existing GPO (GPO-LAB-Users-Test) Linked to the LAB_Users OU was intended to restrict user access, but the actual setting configured inside it was not taking effect.

**Environment:** Windows Server 2022 DC (DC01-server), Windows 10 client (WIN10-CLIENT), lab.local domain, GPO linked to the LAB-Users OU.

## Diagnosis steps

1. Opened Group Policy Management on the DC and confirmed that my GPO was linked to the LAB-Users OU and then I enabled it.
2. Generated a save report and opened the saved html report in the browser to check exactly which settings were configured with this GPO.
3. The report showed one configured setting under User Configuration > Administrative Templates > Control Panel: "Prohibit access to Control Panel and PC settings", with its value set to **Disabled** which I later set to enabled to apply the policy.

**Root cause:** In Group Policy, a setting can be Enabled, Disabled or Not Configured - these are not same as on and off. The policy was configured and in place but was set to disabled.

## Resolution

1. Edited the GPO and enabled the policy.
2. On the clien logged in as tuser the exact user that was configured under LAB-Users OU(Test User) and ran 'gpupdate /force and gpresult /r to apply the change and to verify the change.
3. Attempted to open the Conrol Panel and confirmed the access was denied and the policy is in place.

## Screenshots


![Setting changed to Enabled](images/gpo-controlpanel-enabled.png)

![gpresult confirming the GPO applied](images/gpresult-verify.png)

![Control Panel access blocked](images/controlpanel-blocked.png)