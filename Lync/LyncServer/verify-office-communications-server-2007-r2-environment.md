---
title: 驗證 Office Communications Server 2007 R2 環境
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
ms.openlocfilehash: 0fb67868c9f7eddfe2b11b4238c5fdd1bd14d8e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>驗證 Office Communications Server 2007 R2 環境

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

在使用 Office 通訊伺服器 2007 R2 的共存狀態中部署 Lync Server 2013 之前，您必須確認 Office 通訊伺服器 2007 R2 服務已設定並啟動。

**驗證已使用 Office 通訊伺服器 2007 R2 管理工具啟動該池**

1.  開啟 Office 通訊伺服器 2007 R2 管理工具。

2.  展開 [**目錄林**] 節點，展開 [**標準版伺服器**] 或 [**企業版池**] 節點，然後展開 [池] 或 [伺服器名稱]。

3.  確定服務正在標準版伺服器或企業版池上執行。
    
    ![Office Communications Server 2007 R2 管理主控台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 管理主控台")

**審查針對 Office 通訊伺服器 2007 R2 設定的使用者**

1.  開啟 Office 通訊伺服器 2007 R2 管理工具。

2.  展開 [**目錄林**] 節點，展開 [**標準版伺服器**] 或 [**企業版池**] 節點，然後展開 [池] 或 [伺服器名稱]。

3.  按一下 [**使用者**]。

4.  驗證 Office 通訊伺服器 2007 R2 使用者的清單。
    
    ![OCS 管理工具中的使用者清單](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "OCS 管理工具中的使用者清單")

**驗證舊版 XMPP 聯盟合作夥伴設定**

1.  從舊版 XMPP 伺服器流覽至 [管理工具\\服務] 小程式。

2.  確認已啟動 Office 通訊伺服器 XMPP 閘道服務。
    
    ![Office Communications Server XMPP 閘道服務](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP 閘道服務")

</div>

<span> </span>

</div>

</div>

</div>

