# Orleans.Providers.MSSQLDapper
Optimized Orleans providers for Microsoft SQL Server for In-Memory OLTP and Natively Compiled Stored Procedures

### 9-19-24 Updated to work with Orleans 8.2.0 and .NET 8

### Benchmarks

I ran the benchmarks by using the official Orleans repository's benchmark tool. I had to hack it together because I don't have the bandwidth to write a proper one for this experiment

```
> dotnet run -c Release -f net5.0 -- GrainStorage.AdoNet
Running grain storage benchmark against AdoNet
Performed 266125 persist (read & write) operations with 0 failures in 30420ms.
Average time in ms per call was 11.193829923532308, with longest call taking 7219.5881ms.
Total time waiting for the persistent store was 2978957.9884000355ms.
Elapsed milliseconds: 30453
Press any key to continue ...

> dotnet run -c Release -f net5.0 -- GrainStorage.MSSQLDapper
Running grain storage benchmark against MSSQL + Dapper
Performed 488772 persist (read & write) operations with 0 failures in 30024ms.
Average time in ms per call was 5.908809110382738, with longest call taking 446.4293ms.
Total time waiting for the persistent store was 2888060.4464999917ms.
Elapsed milliseconds: 30112
Press any key to continue ...
```
