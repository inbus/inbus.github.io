#Oracle

##優化
>1.[Oracle性能調整思考方向筆記](Oracle_Performance_Thinking.jpg)

## install oracle client
+ pkexec vi /etc/oraInst.loc
```
inventory_loc=/oracle
inst_group=oinstall 
```
+ mkdir /oracle
+ chmod 775 -R /oracle
+ export ORACLE_HOME=/oracle/product/12.2.0/client_1
+ ./runInstaller -silent -force -noconfig -ignorePrereq 
+ find . |grep libclnts                
+ ln -s libclntsh.so.12.1 libclntsh.so 
+ chmod -R o+rx /oracle
+ vi ~/.bash_profile

```
export ORACLE_HOME=/oracle/product/12.2.0/client_1                    
export TNS_ADMIN=$ORACLE_HOME                                         
export LD_LIBRARY_PATH=$ORACLE_HOME:/usr/local/lib:${LD_LIBRARY_PATH} 
export SQLPATH=$ORACLE_HOME                                           
export PATH=$PATH:$ORACLE_HOME                                        
```
## remove oracle client 
    ./runInstaller -deinstall -home /oracle/product/12.2.0/client_1

