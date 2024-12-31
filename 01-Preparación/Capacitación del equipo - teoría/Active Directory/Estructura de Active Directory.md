Se basa en **BOSQUES** que pueden contener mútiples **DOMINIOS** 
Un **DOMINIO** tiene objetos contenidos (usuarios, ordenadores y grupos).
Tiene muchas **Unidades Organizaces (OU)** incorporadas, como Domain Controllers, Users, Computers, y nuevas OUs se pueden crear según sea necesario (políticas de grupo).

```shell-session
INLANEFREIGHT.LOCAL/
├── ADMIN.INLANEFREIGHT.LOCAL
│   ├── GPOs
│   └── OU
│       └── EMPLOYEES
│           ├── COMPUTERS
│           │   └── FILE01
│           ├── GROUPS
│           │   └── HQ Staff
│           └── USERS
│               └── barbara.jones
├── CORP.INLANEFREIGHT.LOCAL
└── DEV.INLANEFREIGHT.LOCAL
```


