# Ansibleチュートリアル

## Ansibleをインストールしてください

Macの場合

```sh
brew install ansible
```

## EC2を用意してください

- name: `MailServer1`、`MailServer2`
- プラットフォーム： Amazon Linux 2023
- pemフィアル名: `ansible_mail.pem`
- セキュリティグループ: インバウンドルールに22番ポート(SSH)を許可

## 接続先を更新

`inventory_hosts`ファイルの接続先を更新してください

- ansible_host: AWSコンソールからパブリックDNSを確認してください
- ansible_ssh_private_key_file: pemファイルのパスを指定

## 実行してください

```sh
ansible-playbook -i inventory_hosts setup_postfix.ansible.yaml
```