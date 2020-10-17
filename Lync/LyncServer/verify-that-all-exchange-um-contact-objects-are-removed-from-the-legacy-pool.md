---
title: 確認已移除舊版集區中的所有 Exchange UM 連絡人物件
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae8f82016f8dd78c3ecd568e34c3cc408a204ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515950"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>確認已移除舊版集區中的所有 Exchange UM 連絡人物件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-26_

使用 **OCSUmUtil** 工具或 **Get-CsExumContact** 指令程式，確認已從舊版 Office 通訊伺服器 2007 R2 集區中移除 Exchange UM 連絡人物件。 **OCSUmUtil** 位於下列資料夾：

% Program Files% \\ Common files （ \\ Lync Server 2013 \\ 支援 \\OcsUMUtil.exe

用於執行 **OCSUmUtil** 的使用者帳戶必須具備：

  - RTCUniversalServerAdmins 與 RTCUniversalUserAdmins 群組的成員資格 (包括讀取 Exchange Server Unified Messaging 設定的權限)

  - 在指定之組織單位 (OU) 容器中建立連絡人物件的網域權限。

如需使用 **Get-CsExumContact** Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔中的 [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 。

</div>

<span> </span>

</div>

</div>

</div>

