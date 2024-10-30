# apiflask1
from flask import Flask

app = Flask(__name__)

@app.route("/matricula", methods = ['POST'])
def envio():
    data = request.get_json()
    nome = data.get('nome')
    ra = data.get('ra')
    idade = data.get('idade')

    return jsonify({'message': f'Recebido: {nome}, RA: {ra} e Idade:{idade}'}), 200

    #retorno de algo
if(__name__=='__main__'):
    app.run(debug=True)





#Código 2
import requests
import json

url = 'http://127.0.0.1:5000/matricula'
data = {
    'ra': '9329894',
    'nome': 'joão',
    'idade': '16'
}


response = requests.post(url, json=data)

print('StatusCode:', response.status_code)
print('Response Json', response.json())
