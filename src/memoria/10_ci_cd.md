# CI/CD

Firebase ofereix integració amb Github mitjançant Github Actions de manera que cada vegada que fem un push a la branca principal fa un _build_ i un _deploy_ de la nostra app a Firebase Hosting.

Per afegir el suport a aquesta integració:

`firebase init hosting:github`

En cas de ser un repositori d'una organització, aquest comando podria fallar. En eixe cas, la solució la podeu veure ací:

<https://github.com/FirebaseExtended/action-hosting-deploy/issues/40#issuecomment-748017911>

Durant el desenvolupament actiu és millor desactivar aquesta integració ja que el número de minuts al mes que podem usar de manera gratuïta és limitat.

No s'ha d'oblidar que cal emplenar l'apartat _Environments_ al repositori de Github ja que com és obvi, el fitxer `.env` és ignorat.
