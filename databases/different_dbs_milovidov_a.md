Миловидов Алексей "Разработчики остались неизвестны"
====================================================

eventQL 
	интересные архитектурные решения
	C++, похоже на кликхаус	

GPU
Аlenka - gpu database
MapD - open source

PGStorm - open source
BrytlytDB - closed

Kynetica - closed

FPGA
	Kickfire

Offload на SSD

ViyaDB
in-mem, aggregation, координация с Consul, code-generation C++
DBToaster

MemSQL OLTP, analytic C++ code gen -> LLVM
	
Impala LLVМ
	Clickhouse кодогенерация, пологается на обработку векторов

LucidDB
	java + some C++, хорошая кодовая БД, доки, поддержка SQL

Apache Calcite (based LucidDB)
	frontend SQL, used in hive, drill, stamza, mapd

InfiniDB
	proprietary, analytic, column oriented, 
	MariaDB(columnStore)

InfiniSQL
	OLTP, C++,

RethinkDB
	document-oriented, репликация RAFT(протокол консенсунса) и шардирование, С++

XML DB
	Sedna

Константин Книжник
	garret.ru
