向表中插入批量数据的存储过程：
     DELIMITER $$
    CREATE PROCEDURE insert_emp(IN START INT(10),IN max_num INT(10))  
    BEGIN  
    DECLARE i INT DEFAULT 0;   
    #set autocommit =0 把autocommit设置成0  
     SET autocommit = 0;    
     REPEAT  
     SET i = i + 1;  
     INSERT INTO emp (empno, ename ,job ,mgr ,hiredate ,sal ,comm ,deptno ) VALUES ((START+i) ,rand_string(6),'SALESMAN',0001,CURDATE(),2000,400,rand_num());  
     UNTIL i = max_num  
     END REPEAT;  
     COMMIT;  
     END $$


调用数据库函数使用：select 函数名；
调用数据库存储过程：call 存储过程名称；
