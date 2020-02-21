---
title: 確認舊版集區會移除所有 Exchange UM 連絡人物件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7815f78dfa5f2b4aab3f09102a9948498c20cf10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>確認舊版集區會移除所有 Exchange UM 連絡人物件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-26_

使用**OCSUmUtil**工具或**Get-csexumcontact** cmdlet 來確認 Exchange UM 連絡人物件已從舊版 Office Communications Server 2007 R2 集區中移除。 **OCSUmUtil** 位於下列資料夾：

%程式檔案 %\\通用檔案\\Lync Server 2013\\支援\\OcsUMUtil.exe

用於執行 **OCSUmUtil** 的使用者帳戶必須具備：

  - RTCUniversalServerAdmins 與 RTCUniversalUserAdmins 群組的成員資格 (包括讀取 Exchange Server Unified Messaging 設定的權限)

  - 在指定之組織單位 (OU) 容器中建立連絡人物件的網域權限。

如需使用**Get-csexumcontact** cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面文件中的[Get-csexumcontact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 。

</div>

<span> </span>

</div>

</div>

</div>

