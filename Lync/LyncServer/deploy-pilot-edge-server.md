---
title: 部署試驗 Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba616f6a5ce86e0f94c3b52afd60aaba34b7635
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>部署試驗 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

本主題著重于部署 Lync Server 2013 Edge Server 之前，請先注意您應注意的配置設定。 Lync Server 2013 的部署和設定流程非常類似 Lync Server 2010。 本節只著重在部署試驗集區時應該考量的要點。 如需詳細步驟，請參閱部署檔中的「[部署 Lync Server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)」，它會說明部署程式，也會提供外部使用者存取的設定資訊。

As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.

**定義 Edge 集區**

1.  以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。

2.  流覽至 [Lync Server 2013] 節點。 用滑鼠右鍵按一下 [Edge 集區]****，然後按一下 [新增 Edge 集區]****。
    
    ![[定義新的 Edge 集區] 對話方塊](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[定義新的 Edge 集區] 對話方塊")

3.  Edge 集區可以是 [多部電腦集區]**** 或 [單一電腦集區]****。
    
    ![[定義 Edge 集區 FQDN] 對話方塊](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "[定義 Edge 集區 FQDN] 對話方塊")

4.  在「選取功能」**** 頁面上，請勿啟用同盟或 XMPP 同盟。 同盟和 XMPP 同盟目前是透過舊版 Lync Server 2010 Edge Server 路由傳送。 在移轉的後期階段，將會設定這些功能。
    
    ![[選取功能] 對話方塊](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[選取功能] 對話方塊")

5.  接下來，繼續完成下列嚮導頁面：**外部 fqdn**、**定義內部 ip 位址**，以及**定義外部 ip 位址**。

6.  在 [**定義下一個躍點]** 頁面上，選取 Lync Server 2010 Edge 集區的下一個躍點 Director。
    
    ![[定義下一個躍點] 對話方塊](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "[定義下一個躍點] 對話方塊")

7.  在 [**建立前端或**中繼集區] 頁面上，請勿在此時間建立集區與此 Edge 集區的關聯。 外部媒體流量目前是透過舊版 Lync Server 2010 Edge Server 路由傳送。 這項設定到了移轉的後期階段還會再調整。
    
    ![[建立前端集區的關聯] 對話方塊](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "[建立前端集區的關聯] 對話方塊")

8.  按一下 [完成]****，然後 [發行]**** 拓撲。

9.  請遵循部署檔中的[Lync Server 2013 安裝 Edge](lync-server-2013-install-edge-servers.md) server 中的步驟，將檔案安裝在新的 Edge Server 上、設定憑證，然後啟動服務。

在部署檔中遵循在[Lync Server 2013 部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)主題的指導方針非常重要。 本節只提供安裝這些伺服器角色時，部分組態設定的指示。

現在，您應該會同時部署舊版 Lync Server 2010 Edge Server 與 Lync Server 2013 Edge server 部署。 確認部署雙方皆可正常運作、服務已啟用，且您也能管理每個部署，接著，就可以前往下一個階段。

</div>

<span> </span>

</div>

</div>

</div>

