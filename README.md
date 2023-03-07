## Hello! I'm Nic 🤓

I work with digital solutions and study systems development! 

Always looking for new knowledge :)

<div style="display: inline_block"><br>
  <img align="center" alt="Nic-Java" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg">
  <img align="center" alt="Nic-Js" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-plain.svg">
  <img align="center" alt="Nic-HTML" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original.svg">
  <img align="center" alt="Nic-CSS" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original.svg">
  <img align="center" alt="Nic-Python" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg">
  <img align="center" alt="Nic-Raspberry" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/raspberrypi/raspberrypi-original.svg">

 
  ##
 
<div> 
  <a href="https://instagram.com/ni.siq" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white" target="_blank"></a>
  <a href = "mailto:nicole.siq2018@gmail.com"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
  <a href="https://www.linkedin.com/in/nicole-siqueira0101" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
  
</div>

  Nome da Actions:  
name: Snake Game

# Controlador do tempo que sera feito a atualização dos arquivos.
on:
  schedule:
      # Será atualizado a cada 5 horas.
    - cron: "0 */5 * * *"

# Permite executar na na lista de Actions (utilizado para testes de build).
  workflow_dispatch:

# Regras
jobs:
  build:
    runs-on: ubuntu-latest
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Repositorio que será utilizado para gerar os arquivos.
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: nisiq #Seu usuario
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

      - run: git status

      # Para as atualizações.
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
    # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

# name: Generate Datas

# on:
#   schedule: # execute every 12 hours
#     - cron: "* */12 * * *"
#   workflow_dispatch:

# jobs:
#   build:
#     name: Jobs to update datas
#     runs-on: ubuntu-latest
#     steps:
#       # Snake Animation
#       - uses: Platane/snk@master
#         id: snake-gif
#         with:
#           github_user_name: raissarossi
#           svg_out_path: dist/github-contribution-grid-snake.svg

#       - uses: crazy-max/ghaction-github-pages@v2.1.3
#         with:
#           target_branch: output
#           build_dir: dist
#         env:
#           GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
  
