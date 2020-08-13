---
title: Lync Server 2013：在 Microsoft Exchange Server 上設定整合通訊，以與 Lync Server 搭配使用
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
ms.openlocfilehash: 01d3d90f738741c2815d01041a7d2293e978cd2b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>在 Microsoft Exchange Server 上設定整合通訊以搭配 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-11_

<div>


> [!IMPORTANT]  
> 如果您想要使用 Exchange 整合通訊 (UM) 提供適用于 Enterprise Voice 使用者的呼叫回應、Outlook Voice Access 或自動語音應答服務，請參閱規劃檔中的<A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Exchange 整合通訊（Lync Server 2013</A> ）中的 [規劃 Exchange 整合通訊整合]，然後依照本節中的指示進行。



</div>

若要設定 Exchange 整合通訊 (UM) 以使用 Enterprise Voice，您必須執行下列工作：

  - 在執行 Exchange 整合通訊 (UM) 服務的伺服器上設定憑證
    
    <div>
    

    > [!NOTE]  
    > 將所有用戶端存取和信箱伺服器新增至所有 UM SIP URI 撥號對應表。 如果不是，則輸出通話路由不會如預期般運作。

    
    </div>

  - 視需要建立一個或多個 UM SIP URI 撥號對應表，以及訂閱者存取電話號碼，然後建立對應的 Lync Server 撥號對應表。

  - 使用**exchucutil.ps1**腳本執行下列作業：
    
      - 建立 UM IP 閘道。
    
      - 建立 UM 群組搜尋。
    
      - 授與 Lync Server 2013 讀取 UM Active Directory 網域服務物件的許可權。

  - 建立 UM 自動語音應答物件。

  - 建立訂閱者存取物件。

  - 為每個使用者建立 SIP URI，並將使用者與 UM SIP URI 撥號對應表相關聯。

<div>

## <a name="requirements-and-recommendations"></a>需求和建議

在您開始之前，本節中的檔會假設您已部署下列 Exchange 2013 角色： Client Access 和信箱。 在 Microsoft Exchange Server 2013 中，Exchange UM 會在這些伺服器上以服務的身分執行。

如需部署 Exchange 2013 的詳細資訊，請參閱 Exchange 2013 TechNet 程式庫，網址為[https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)

也請注意以下事項：

  - 如果已在多個樹系中安裝 Exchange UM，則必須針對每個 UM 樹系執行 Exchange Server 整合步驟。 此外，每個 UM 樹系都必須設定為信任已部署 Lync Server 2013 的樹系，而且部署 Lync Server 2013 的樹系必須設定為信任每個 UM 樹系。

  - 在執行整合通訊服務的 Exchange 伺服器角色，以及執行 Lync Server 2013 的伺服器上執行整合步驟。 在您執行 Lync Server 2013 整合步驟之前，您應該先執行 Exchange Server 整合通訊整合步驟。
    
    <div>
    

    > [!NOTE]  
    > 若要查看在哪些伺服器及系統管理員角色上執行哪些整合步驟，請參閱<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">整合內部部署整合通訊和 Lync Server 2013 的部署程式</A>。

    
    </div>

在執行 Exchange UM 的每一部伺服器上都必須提供下列工具：

  - Exchange 管理命令介面

  - 指令碼 **exchucutil.ps1**，它會執行下列工作：
    
      - 為每個 Lync Server 2013 建立 UM IP 閘道。
    
      - 為每一個閘道建立群組搜尋。 每個群組搜尋的引導識別碼會指定與閘道相關聯之前端集區或 Standard Edition server 所使用的 UM SIP URI 撥號對應表。
    
      - 授與 Lync Server 2013 在 Active Directory 網域服務中讀取 Exchange UM 物件的許可權。

</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在執行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [在 Microsoft Exchange 上設定 Lync Server 2013 的整合通訊](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

