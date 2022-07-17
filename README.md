# mysql-banco-de-dados-simples
Criei esse banco utilizando a ferramente visual MySQL Workbench. Criando um banco de dados básico para treinar, com comandos básicos e fazendo relacionamento de tabelas. 
Criei esse banco utilizando a ferramente visual MySQL Workbench.
Criando um banco de dados básico para treinar, com comandos básicos e fazendo relacionamento de tabelas.


create database if not exists csgo;


use csgo;


create table if not exists topjogadores (
idjogador tinyint(2) auto_increment,
jogador varchar(30),
posicaojogador tinyint(2),
primary key (idjogador)
) default charset = utf8;


alter table topjogadores add postime tinyint(2);


alter table topjogadores
add foreign key (postime)
references toptimes (idtime);


alter table topjogadores change posicaojogador posicaojogador varchar(30);


insert into topjogadores values 
(default, 'rain', 'rifler', '1'),
(default, 'b1t', 'rifler e awper', '2'),
(default, 'spinx', 'rifler(luker)','3'),
(default, 's1mple', 'awper', '2'),
(default, 'monesy', 'awper', '7'),
(default, 'zywoo', 'awper e rifler', '8'),
(default, 'stavn', 'rifler e awper', '9'),
(default, 'fer', 'rifler e entry fragger', '1'),
(default, 'degster', 'awper', '13'),
(default, 'dycha', 'rifler', '3');
    
desc topjogadores;


select * from topjogadores;

------------------------------------------------------


create table if not exists toptimes (
idtime tinyint(2) auto_increment,
times varchar(10),
posicaotime tinyint(2),
primary key(idtime)
) default charset = utf8;


select jogador, postime, times
from topjogadores join toptimes
on idtime = postime;


alter table toptimes change times times varchar(30);


insert into toptimes values
(default, 'faze clan', '1'),
(default, 'natus vincere', '2'),
(default, 'ence', '3'),
(default, 'cloud9', '4'),
(default, 'furia esports', '5'),
(default, 'big', '6'),
(default, 'g2 esports', '7'),
(default, 'team vitality', '8'),
(default, 'heroic', '9'),
(default, 'ninjas in pyjamas', '10');


desc toptimes;


select * from toptimes;


------------------------------------------------------
