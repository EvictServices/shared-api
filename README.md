# shared-api


sudo apt install docker-compose

docker-compose up -d warp
docker-compose up -d chrome

python3.12 -m venv .venv
source .venv/bin/activate
apt-get install -y python3-dev && pip install netifaces
python3.12 -m pip install --upgrade pip
python3.12 -m pip install -r requirements.txt
playwright install
playwright install-deps
pip install scalar-fastapi

python3.12 -m api

# fix 
cd chrome && docker-compose down
docker-compose down && docker-compose up -d
docker system prune -f
docker rm -f chrome
docker rm -f warp chrome || true
docker ps -a | grep -E 'chrome|warp'
docker-compose down && docker-compose up -d
docker stop chrome warp || true && docker rm -f chrome warp || true