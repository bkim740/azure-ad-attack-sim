# Policy Matrix (Mapping Users/Groups → Policies/Roles)

| Group        | Intended Roles (min required)                | Conditional Access (CA)                              |
|--------------|----------------------------------------------|------------------------------------------------------|
| Admins       | Privileged Role Administrator (lab only), Security Reader | Require MFA, Block legacy auth, Device compliant OR trusted location, CA enforced |
| Executives   | None                                         | Require MFA, Disallow legacy auth, CA enforced       |
| Employees    | None                                         | Require MFA, Disallow legacy auth, CA enforced       |

> Tailor the above to your lab. Keep privileged roles *minimal* and use PIM/eligible where possible.
