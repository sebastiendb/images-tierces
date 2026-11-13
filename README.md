# images-tierces

Reconstruit l'image Docker d'un projet amont depuis un tag précis, quand l'éditeur ne publie pas d'image corrigée.

    gh workflow run construire.yml -R sebastiendb/images-tierces \
      -f depot=CapSoftware/Cap -f ref=cap-v0.6.3 -f dockerfile=apps/web/Dockerfile \
      -f image=cap-web -f tag=v0.6.3 -f env_racine='WEB_URL=http://localhost:3000;NEXT_PUBLIC_DOCKER_BUILD=true'

Résultat : `ghcr.io/sebastiendb/<image>:<tag>` (public), à poser par `coolify service-image`.
