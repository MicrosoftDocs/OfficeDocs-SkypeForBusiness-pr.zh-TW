---
title: Lync Server 2013：設定 Microsoft Exchange Server 上的 Unified Messaging 以搭配 Lync Serve 使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e2bc41d4fa0411c4184c0edda35d6d0cd98df9a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>設定 Microsoft Exchange Server 上的 Unified Messaging 以搭配 Lync Server 2013 使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-11_

<div>


> [!IMPORTANT]  
> 如果您想要使用 Exchange 整合訊息（UM）來提供呼叫應答、Outlook Voice Access 或適用于企業語音使用者的自動助理服務，請參閱規劃檔中的<A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Lync Server 2013 中的 Exchange 整合訊息整合規劃</A>，然後依照本節中的指示進行。



</div>

若要設定 Exchange 整合通訊（UM）以搭配企業語音使用，您必須執行下列工作：

  - 在運行 Exchange 整合通訊（UM）服務的伺服器上設定憑證
    
    <div>
    

    > [!NOTE]  
    > 將所有用戶端存取和信箱伺服器新增到所有 UM SIP URI 撥號方案。 如果不是，傳出通話路由將無法如期運作。

    
    </div>

  - 視需要建立一個或多個 UM SIP URI 撥號方案，以及訂閱者存取電話號碼，然後建立對應的 Lync Server 撥號方案。

  - 使用**exchucutil. ps1**腳本來：
    
      - 建立 UM IP 閘道。
    
      - 建立 UM 查尋群組。
    
      - 授與 Lync Server 2013 讀取 UM Active Directory 網域服務物件的許可權。

  - 建立 UM 自動助理物件。

  - 建立訂閱者存取物件。

  - 為每位使用者建立 SIP URI，並將使用者與 UM SIP URI 撥號方案產生關聯。

<div>

## <a name="requirements-and-recommendations"></a>需求與建議

在開始之前，本節中的檔假設您已部署下列 Exchange 2013 角色：用戶端存取和信箱。 在 Microsoft Exchange Server 2013 中，Exchange UM 在這些伺服器上以服務的方式執行。

如需有關部署 Exchange 2013 的詳細資訊，請參閱 Exchange 2013 TechNet 文件庫，網址為[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

另請注意下列事項：

  - 如果 Exchange UM 安裝在多個目錄林中，則必須針對每個 UM 林執行 Exchange Server 整合步驟。 此外，每個 UM 目錄林都必須設定為信任已部署 Lync Server 2013 的林，而部署 Lync Server 2013 的林必須設定為信任每個 UM 目錄林。

  - 整合步驟是在執行整合訊息服務的 Exchange 伺服器角色，以及在執行 Lync Server 2013 的伺服器上執行。 在執行 Lync Server 2013 整合步驟之前，您應該執行 Exchange Server 整合訊息整合的步驟。
    
    <div>
    

    > [!NOTE]  
    > 若要查看對哪些伺服器以及哪些系統管理員角色執行哪些整合步驟，請參閱<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">整合內部部署整合訊息和 Lync Server 2013 的部署程式</A>。

    
    </div>

在執行 Exchange UM 的每個伺服器上，都必須提供下列工具：

  - Exchange 管理命令介面

  - 腳本**exchucutil. ps1**，可執行下列任務：
    
      - 為每個 Lync Server 2013 建立 UM IP 閘道。
    
      - 為每個閘道建立一個 [查尋] 群組。 每個查尋群組的先導識別碼，會指定與閘道相關聯的前端池或標準版伺服器所使用的 UM SIP URI 撥號方案。
    
      - 授予 Lync Server 2013 在 Active Directory 網域服務中讀取 Exchange UM 物件的許可權。

</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在運行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [在 Microsoft Exchange for Lync Server 2013 中設定整合通訊](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

