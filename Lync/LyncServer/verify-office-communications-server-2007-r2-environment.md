---
title: 確認 Office Communications Server 2007 R2 環境
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 885b1b08ef2d02c6a3cb3a77b83ca832e70281a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>確認 Office Communications Server 2007 R2 環境

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 10-16_

之前部署處於共存狀態與 Office Communications Server 2007 R2 的 Lync Server 2013，您必須確認 Office Communications Server 2007 R2 服務已設定且啟動。

**確認已啟動集區，使用 Office Communications Server 2007 R2 系統管理工具**

1.  開啟 [Office Communications Server 2007 R2 系統管理工具]。

2.  依序展開 **[樹系]** 節點及 **[Standard Edition Server]** 或 **[Enterprise Pool]** 節點，然後展開集區或伺服器名稱。

3.  確定服務執行於 Standard Edition server 或 Enterprise pool。
    
    ![Office Communications Server 2007 R2 系統管理主控台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 系統管理主控台")

**檢閱 Office Communications Server 2007 r2 設定的使用者**

1.  開啟 [Office Communications Server 2007 R2 系統管理工具]。

2.  依序展開 **[樹系]** 節點及 **[Standard Edition Server]** 或 **[Enterprise Pool]** 節點，然後展開集區或伺服器名稱。

3.  按一下 [使用者]****。

4.  確認 Office Communications Server 2007 R2 使用者清單。
    
    ![NM-OCS-13-2ND 系統管理工具中的清單中的使用者](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "NM-OCS-13-2ND 系統管理工具中的清單中的使用者")

**確認舊版 XMPP 同盟協力廠商設定**

1.  從舊版 XMPP 伺服器瀏覽至系統管理工具\\服務] 小程式。

2.  確認 Office Communications Server XMPP 閘道服務已啟動。
    
    ![Office Communications Server XMPP 閘道服務](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP 閘道服務")

</div>

<span> </span>

</div>

</div>

</div>

