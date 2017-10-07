
app:
	go build -o app app.go

app_deploy:
	GOOS=linux go build -o app_deploy app.go

deploy: app_deploy
	echo start deploy by $(USER) | notify_slack
	ssh isu sudo -H systemctl stop isuxi.go.service
	rsync templates/ -ahv isu:/home/isucon/webapp/go/templates/
	scp app_deploy isu:/home/isucon/webapp/go/app
	ssh isu sudo -H systemctl start isuxi.go.service
	echo finish deploy by $(USER) | notify_slack
