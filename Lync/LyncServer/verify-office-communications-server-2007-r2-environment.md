---
title: 驗證 Office 通訊伺服器 2007 R2 環境
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f4107877c237abef92233dbca88cf7060fdca25
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515940"
---
# <a name="verify-office-communications-server-2007-r2-environment"></a>驗證 Office 通訊伺服器 2007 R2 環境

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

在使用 Office 通訊伺服器 2007 R2 在共存狀態中部署 Lync Server 2013 之前，您必須確認已設定並啟動 Office 通訊伺服器 2007 R2 服務。

**驗證是否已使用 Office 通訊伺服器 2007 R2 系統管理工具啟動集區**

1.  開啟 Office 通訊伺服器 2007 R2 系統管理工具。

2.  依序展開 **[樹系]** 節點及 **[Standard Edition Server]** 或 **[Enterprise Pool]** 節點，然後展開集區或伺服器名稱。

3.  確定服務正在 Standard Edition server 或 Enterprise pool 上執行。
    
    ![Office 通訊伺服器 2007 R2 管理主控台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office 通訊伺服器 2007 R2 管理主控台")

**檢查針對 Office 通訊伺服器 2007 R2 設定的使用者**

1.  開啟 Office 通訊伺服器 2007 R2 系統管理工具。

2.  依序展開 **[樹系]** 節點及 **[Standard Edition Server]** 或 **[Enterprise Pool]** 節點，然後展開集區或伺服器名稱。

3.  按一下 **[使用者]**。

4.  確認 Office 通訊伺服器 2007 R2 使用者的清單。
    
    ![OCS 系統管理工具中的使用者清單](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "OCS 系統管理工具中的使用者清單")

**驗證舊版 XMPP 同盟協力廠商設定**

1.  在舊版 XMPP 伺服器上，流覽至 [系統管理工具 \\ 服務] 小程式。

2.  確認已啟動 Office 通訊伺服器 XMPP 閘道服務。
    
    ![Office 通訊伺服器 XMPP 閘道服務](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office 通訊伺服器 XMPP 閘道服務")

</div>

<span> </span>

</div>

</div>

</div>

