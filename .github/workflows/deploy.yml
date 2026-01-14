name: Deploy LAMP App

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - name: Deploy to EC2
      uses: appleboy/ssh-action@v1.0.3
      with:
        host: ${{ secrets.SERVER_IP }}
        username: ec2-user
        key: ${{ secrets.SSH_PRIVATE_KEY }}
        script: |
          cd /var/www/html
          git pull origin main
          sudo systemctl restart httpd
