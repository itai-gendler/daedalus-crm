---
{
  "kind": "configuration",
  "of": "capability-scenario",
  "settings": [
    {
      "entity": "service-config",
      "fact": "Verification policy"
    }
  ],
  "takesEffect": "The web registration form reads the deployment policy at rendering; the native email-start response selects its next input step. Code sending and final registration independently read current policy on each invocation.",
  "stability": "An open form is not an authority snapshot: changing SIGNUP_VERIFY changes subsequent server decisions. Missing or any value other than 1 means no code; a newly required code can refuse a submission from an older form. Existing accounts are retained.",
  "alternatives": [
    {
      "id": "register-account-p01",
      "selectedWhen": "Deployment does not require a verification code."
    },
    {
      "id": "register-account-p02",
      "selectedWhen": "Deployment requires a verification-code actor input."
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/signup/SignupForm.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/signup/actions.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/signup-policy.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/lib/tenant/signup.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/app/api/account/signup/start/route.ts"
    }
  ]
}
---

# Registration Verification Policy

The existing configuration selects the supported actor input path described by these alternatives.
