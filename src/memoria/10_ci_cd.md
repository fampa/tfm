# CI/CD

Firebase ofereix integració amb Github de manera que cada vegada que fem un push a la branca principal fa un _build_ i un _deploy_ de la nostra app a Firebase Hosting.

Per afegir el suport a aquesta integració:

`firebase init hosting:github`

En cas de ser un repositori d'una organització, aquest comando podria fallar. En eixe cas, la solució la podeu veure ací:

<https://github.com/FirebaseExtended/action-hosting-deploy/issues/40#issuecomment-748017911>
