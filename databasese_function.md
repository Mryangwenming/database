随机产生字符串：
    DELIMITER $$
    CREATE FUNCTION rand_string(n INT) RETURNS VARCHAR(255)
    BEGIN
     DECLARE chars_str VARCHAR(100) DEFAULT 'abcdefghijklmnopqrstuvwxyzABCDEFJHIJKLMNOPQRSTUVWXYZ';
     DECLARE return_str VARCHAR(255) DEFAULT '';
     DECLARE i INT DEFAULT 0;
     WHILE i < n DO
     SET return_str =CONCAT(return_str,SUBSTRING(chars_str,FLOOR(1+RAND()*52),1));
     SET i = i + 1;
     END WHILE;
     RETURN return_str;
    END $$


随机产生编号：
    DELIMITER $$
    CREATE FUNCTION rand_num( ) 
    RETURNS INT(5)  
    BEGIN   
     DECLARE i INT DEFAULT 0;  
     SET i = FLOOR(100+RAND()*10);  
    RETURN i;  
     END $$

