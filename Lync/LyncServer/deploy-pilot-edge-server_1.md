---
title: 部署試驗 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cbf3be6dd47f794768ba0f3c8140e7124a1cabb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>部署試驗 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-19_

本主題會醒目提示您應該要知道再部署 Lync Server 2013 Edge Server 的組態設定。 本節只著重在試驗 Edge 集區部署期間應該考量的要點。 如需詳細步驟，請參閱部署文件，其中說明的部署程序，同時也讓外部使用者存取的組態資訊中的[Deploying Lync Server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)。

啟動 [定義新 Edge 集區精靈]**** 逐步完成設定，請檢閱下列步驟中的重要組態設定。請注意，下面只列出了「定義新 Edge 集區精靈」**** 部分頁面而已。

**定義 Edge 集區**

1.  使用拓撲產生器，開啟試驗集區拓撲。

2.  瀏覽至 [Lync Server 2013] 節點。 用滑鼠右鍵按一下 [Edge 集區]****，然後按一下 [新增 Edge 集區]****。
    
    ![定義新的 Edge 集區] 對話方塊](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "定義新的 Edge 集區] 對話方塊")

3.  Edge 集區可以是 [多部電腦集區]**** 或 [單一電腦集區]****。
    
    ![定義 Edge 集區 FQDN] 對話方塊](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "定義 Edge 集區 FQDN] 對話方塊")

4.  在「選取功能」**** 頁面上，請勿啟用同盟或 XMPP 同盟。 同盟和 XMPP 同盟目前會透過舊版 Office Communications Server 2007 R2 Edge Server 路由傳送。 在移轉的後期階段，將會設定這些功能。
    
    ![[選取功能] 對話方塊](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[選取功能] 對話方塊")

5.  接著，繼續完成下列精靈頁面：「選取 IP 選項」****、「外部 FQDN」****、「定義內部 IP 位址」**** 及「定義外部 IP 位址」****。

6.  在 [**定義下一個躍點**] 頁面上，選取 Lync Server 2013 Edge 集區的下一個躍點的 Director。
    
    ![定義新的 Edge 集區] 對話方塊中下, 一個躍點集區] 清單](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "定義新的 Edge 集區] 對話方塊中下, 一個躍點集區] 清單")

7.  在 [**建立關聯的前端集區**] 頁面不關聯的集區與此 Edge 集區這一次。 透過舊版 Office Communications Server 2007 R2 Edge Server 目前路由外部媒體流量。 這項設定到了移轉的後期階段還會再調整。
    
    ![定義新的 Edge 集區] 對話方塊](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "定義新的 Edge 集區] 對話方塊")

8.  按一下 [完成]****，然後 [發行]**** 拓撲。

9.  請遵循[Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md)中新的 Edge Server 上安裝檔案、 設定憑證及啟動服務部署 > 文件中的步驟。

都是非常重要的是您遵循部署文件中的主題[部署 Lync Server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)中的指導方針。 本節只提供安裝這些伺服器角色時，部分組態設定的指示。

現在，您應該有舊版的 Office Communications Server 2007 R2 Edge server 部署，所管制 BackCompatSite，同時搭配 Lync Server 2013 Edge server 部署中的指示。 同盟設定為使用 Office Communications Server 2007 R2 Director。 確認部署雙方皆可正常運作、服務已啟用，且您也能管理每個部署，接著，就可以前往下一個階段。

![顯示 NM-OCS-14-2ND Edge Server 拓撲產生器](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "顯示 NM-OCS-14-2ND Edge Server 拓撲產生器")

</div>

<span> </span>

</div>

</div>

</div>

