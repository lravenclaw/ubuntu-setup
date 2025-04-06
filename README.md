# Dev Machine Setup with Ansible

Этот проект автоматически настраивает вашу рабочую станцию для Python/Go/DevOps разработки с использованием Ansible.

## Требования

- Ubuntu-based система
- Установлен Ansible

Не забудьте изменить `user` в `dev-setup.yml` в `vars`.

## Использование

### 1. Установка Ansible

Перед тем как запустить playbook, убедитесь, что Ansible установлен на вашей машине. Для установки Ansible на Ubuntu выполните следующие команды:

```bash
sudo apt update
sudo apt install ansible
```

### 2. Клонируйте или распакуйте репозиторий

Если вы скачали архив, просто распакуйте его. Если хотите работать с репозиторием напрямую, клонируйте его с помощью git:

```bash
git clone https://github.com/your-repository/dev-setup.git
cd dev-setup
```

Замените your-repository на название вашего репозитория, если это необходимо.

### 3. Запуск playbook

Теперь, когда инвентарь настроен, можно запустить playbook:

```bash
ansible-playbook -i inventory.ini dev-setup.yml
```

Если ваша система требует использования sudo, убедитесь, что у вас есть права для выполнения команд с использованием sudo без пароля. В противном случае используйте флаг --ask-become-pass, чтобы ввести пароль:

```bash
ansible-playbook -i inventory.ini dev-setup.yml --ask-become-pass
```

### 4. Убедитесь, что всё работает

После выполнения playbook, все установленные программы и конфигурации должны быть готовы:

- Guake терминал с привязанной клавишей F1.

- SSH-ключи для GitHub и GitLab сгенерированы.

- Установлены все необходимые инструменты (VS Code, PyCharm, Redis, RabbitMQ, Docker и т. д.).

### 5. Дополнительные настройки

Если вам нужно внести дополнительные изменения в настройки или установить дополнительные программы, отредактируйте файл dev-setup.yml, добавив необходимые задачи.

Что устанавливает playbook:

Системные пакеты:

- Git, Curl, Docker, PostgreSQL, Redis, RabbitMQ и другие утилиты.

Настройка окружения для Python:

- Установлены Python, pip, venv, Go и другие инструменты.

- Установка и настройка рабочего окружения (Pytest, SQLAlchemy, Celery, Redis и другие).

Программы:

- KeePassXC

- VS Code, Postman, Telegram, Discord, PyCharm Professional, Notion

- Guake терминал с горячей клавишей F1

SSH-ключи:

- Генерация SSH ключей для GitHub и GitLab (dostavix, ledrus).

### Для настройки SSH-ключей

Чтобы добавить SSH-ключи на GitHub и GitLab:

Получите ключи:

```bash
    cat ~/.ssh/id_ed25519_github.pub
    cat ~/.ssh/id_ed25519_gitlab_dostavix.pub
    cat ~/.ssh/id_ed25519_gitlab_ledrus.pub
```

Добавьте их на соответствующие платформы.

### Дополнительные настройки

Не забудье настроить zsh в guake terminal, а также настроить отдельные стреды разработки.
