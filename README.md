# ucrm_single
docker + laravel + vue3でuCRMシステム開発の見本用<br>
<br>
# git clone後のインストール<br>
ucrm_single/add/直下の.env.exampleをコピペで同階層に.envを作成。<br>
ただし、ucrm_single/直下のapp.envとdb.envで上書きするから、この.envを書き換える必要なし。<br>
<br>
## コンテナを起動<br>
docker compose up -d<br>
<br>
## appコンテナに入り、インストール<br>
docker compose exec app bash<br>
composer install<br>
npm install<br>
php artisan key:generate<br>
npm run build<br>

##  データベースのテーブルとダミーレコードを生成（appコンテナ内のままで行う）<br>
php artisan migrate:fresh --seed<br>
<br>
# ブラウザでアクセス<br>
http://localhost:81　でブラウザで開く<br>
ポート番号81を変えたいなら、ucrm_single/直下のdocker_compose.ymlの「81:80」を適時編集してください。<br>
