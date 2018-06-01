# Nuget_Readme

1. 下載NuGet

跟著網址create一個新的feed (管理你的pkg的地方)
https://docs.microsoft.com/en-us/vsts/package/get-started-nuget?view=vsts

2. 封包

從網址中下載 Nuget+VSTS
打開 powershell 到下載Nuget的地方執行 pack
每個
以這個的為例
.\NuGet.exe pack ..\..\EPACrawler\EPACrawler\EPACrawler.csproj
.\NuGet.exe push -source "testpackage" -ApiKey VSTS ..\FirstCrawler\FirstCrawler.1.0.0.n
upkg
