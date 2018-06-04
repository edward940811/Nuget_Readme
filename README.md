# Nuget_Readme

1. 下載NuGet

跟著網址create一個新的feed (管理你的pkg的地方)

https://docs.microsoft.com/en-us/vsts/package/get-started-nuget?view=vsts

創完後在visual studio team service 的 build and release 區塊點選connect to feed

會出現這個feed的管理辦法 

   1-1 從第一格 網址中下載 Nuget+VSTS
   1-2 第二格等一下會用到


2. 封包

要上傳到自己的nuget server第一步要先把你的專案變成nupkg
每一個solution 在 build 完成後都會有dll檔包含在專案資料夾裡面

若只有一個csproj要打包
打開 powershell 到下載Nuget的地方執行 pack

ex.

PS C:\Users\repos> Nuget.exe pack [../Myproject/test.csproj]

PS C:\Users\repos> NuGet.exe pack ..\myPackage.csproj

之後要將你建立的feed加到等等要push 的source中
直接複製 1-2 ,1-3 的網址,一樣執行Nuget.exe執行這兩行
ex.

PS C:\Users\repos> Nuget.exe sources Add -Name "test" -Source "http://xxxxxxxxxxxxxxxx.json"

PS C:\Users\repos> .\NuGet.exe push -source "testpackage" -ApiKey VSTS .\myPackage.1.0.0.nupkg

%% 不要用nuget.org已經有的package名稱 ex. Calculator.nupkg
%% 若需要瀏覽注意是否有Package Management權限
