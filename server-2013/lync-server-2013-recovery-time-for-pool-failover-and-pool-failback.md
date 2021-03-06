﻿---
title: Lync Server 2013 集區容錯回復與集區容錯移轉的復原時間
TOCTitle: 集區容錯回復與集區容錯移轉的復原時間
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/zh-tw/library/JJ205079(v=OCS.15)
ms:contentKeyID: 49291653
ms.date: 08/10/2015
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的集區容錯回復與集區容錯移轉的復原時間

 

_**上次修改主題的時間：** 2012-09-10_

針對集區容錯移轉與集區容錯回復，適用於復原時間目標 (RTO) 的工程目標是 30 分鐘。此為在系統管理員判斷發生嚴重損壞並初始容錯移轉程序之後進行容錯移轉所需的時間。其中不包含系統管理員用來評估狀況並進行決策的時間，也不包含使用者在完成容錯移轉之後再次登入的時間。

針對集區容錯移轉與集區容錯回復，適用於復原點目標 (RPO) 的工程目標是 30 分鐘。這表示可能因為發生嚴重損壞、因為備份服務的複寫延遲而遺失之資料的測量時間。例如，如果集區在上午 10 點失效且 RPO 為 30 分鐘，則在上午 9:30 和上午 10 點之間寫入集區的資料可能不會複寫至備份集區，並會遺失。

本文件中所有的 RTO 和 RPO 數字會假設這兩個資料中心位於相同的地理區域，而且在這兩個網站之間具備高速、低延遲的傳輸。這些數字都是針對含有 40,000 位同時使用的作用中使用者，以及針對 Lync 啟用之 200,000 位使用者的集區，測量有關資料複寫中沒有待處理項目之預先定義的使用者模型而得到的。它們主要是根據效能測試與驗證來進行變更。

