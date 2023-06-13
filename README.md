select Sum(Quantity*UnitPrice) as TotalAmount
from Sale Table 
-------------------------
select distinct Customer as CustomerCount
from Sale Table 
--------------------------

select Count(Quantity) as TotalCount as Product
from Sale Table 
Group by Product
----------------------------------
select s.Customer ,
sum(Quantity*UnitPrice) as TotalAmount ,
Count(*) FactorCount ,
Count(Quantity) as QuantityCount,
from Sale Table  s 
Group by Customer 
having s.Quantity*s.UnitPrice*sp.ProfitRatio/100> 1500
-------------------------------

select (select Sum(s.Quantity*s.UnitPrice*sp.ProfitRatio/100) as TotalAmount
from Sale Table  s 
left join Sales Profit sp
on s.Product=sp.Product) - 
(select Sum(Quantity*UnitPrice) as TotalAmount
from Sale Table ) as TotalProfitAnmount


select (select Sum(s.Quantity*s.UnitPrice*sp.ProfitRatio/100) as TotalAmount
from Sale Table  s 
left join Sales Profit sp
on s.Product=sp.Product) - TotalProfitAnmountPercent

--------------------------------------------
(select Sum(Quantity*UnitPrice) as TotalAmount
from Sale Table )/100 as 
---------------------
select Count(select Distinct ID
from Sale Table)
