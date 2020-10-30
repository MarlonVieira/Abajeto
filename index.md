# DOCUMENTAÇÃO PROJETO DO ABAJUR

## 1. Introdução
O presente trabalho tem como finalidade pesquisar, discutir, elaborar, desenvolver e publicar um projeto em grupo. O qual consiste em criar um esquema elétrico para realizar determinadas tarefas, as quais foram discutidas pela equipe. Para a criação do mesmo foi utilizado ferramentas online gratuitas e vídeo aulas disponibilizadas na plataforma Moodle.
## 2. Objetivos

## 3. Materiais utilizados
### Lista de Materiais
 - Arduino Uno R3;
 - Lâmpada;
 - Sensor de distância ultrassônico ;
 - 6 Fios.

### Lista de Ferramentas
 - Tinkercad;
 - StackEdit;
 - GitHub.

## 4. Esquema Elétrico

## 5. Código
```markdown
	int palmas = 250; 
	int som;  
	int status = 0;  

	long readUltrasonicDistance(int triggerPin, int echoPin)
	{
	  pinMode(triggerPin, OUTPUT); 
	  digitalWrite(triggerPin, LOW);
	  delayMicroseconds(2);

	  digitalWrite(triggerPin, HIGH);
	  delayMicroseconds(10);
	  digitalWrite(triggerPin, LOW);
	  pinMode(echoPin, INPUT);
	  return pulseIn(echoPin, HIGH);
	}

	void setup()
	{
	  Serial.begin(9600); 
	  pinMode(2, INPUT);
	  pinMode(13, OUTPUT);
	}

	void loop()
	{
	  som = 0.01723 * readUltrasonicDistance(2, A1);
	  Serial.print("Valor que o microfone esta me enviando: ");
	  Serial.println(som);
	  if ((som > palmas) && (status == 0))
	  {
	    digitalWrite(13, HIGH);
	    status = 1;
	    delay(1000); 
	  }
	  else if ((som > palmas) && (status == 1))
	  {
	    digitalWrite(13, LOW);
	    status = 0;
	    delay(1000);
	  }
	}


```

## 6. Resultados

## 7. Desafios encontrados

