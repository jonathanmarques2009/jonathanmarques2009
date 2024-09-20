import requests

# URL do Kaspersky Security Center API
url = "http://kscserver:13299/api/v1.0/tasks"

# Dados para criar uma nova tarefa de atualização
task_data = {
    "name": "Tarefa de Atualização de Assinaturas",
    "type": "update_signatures",
    "schedule": {
        "repeatInterval": 3600
    }
}

# Autenticação e headers
headers = {
    "Authorization": "Bearer your_api_token",
    "Content-Type": "application/json"
}

# Enviando requisição para criar a tarefa
response = requests.post(url, json=task_data, headers=headers)

if response.status_code == 201:
    print("Tarefa de atualização criada com sucesso.")
else:
    print("Erro ao criar tarefa:", response.status_code, response.text)
