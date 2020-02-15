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
ms.openlocfilehash: 79183039cedc058d479d52fa80ce09a70ffd73b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="9305d-102">確認舊版集區會移除所有 Exchange UM 連絡人物件</span><span class="sxs-lookup"><span data-stu-id="9305d-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9305d-103">_**主題上次修改日期：** 2012年-09-26_</span><span class="sxs-lookup"><span data-stu-id="9305d-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="9305d-104">使用**OCSUmUtil**工具或**Get-csexumcontact** cmdlet 來確認 Exchange UM 連絡人物件已從舊版 Office Communications Server 2007 R2 集區中移除。</span><span class="sxs-lookup"><span data-stu-id="9305d-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="9305d-105">**OCSUmUtil** 位於下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="9305d-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="9305d-106">%程式檔案 %\\通用檔案\\Lync Server 2013\\支援\\OcsUMUtil.exe</span><span class="sxs-lookup"><span data-stu-id="9305d-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="9305d-107">用於執行 **OCSUmUtil** 的使用者帳戶必須具備：</span><span class="sxs-lookup"><span data-stu-id="9305d-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="9305d-108">RTCUniversalServerAdmins 與 RTCUniversalUserAdmins 群組的成員資格 (包括讀取 Exchange Server Unified Messaging 設定的權限)</span><span class="sxs-lookup"><span data-stu-id="9305d-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="9305d-109">在指定之組織單位 (OU) 容器中建立連絡人物件的網域權限。</span><span class="sxs-lookup"><span data-stu-id="9305d-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="9305d-110">如需使用**Get-csexumcontact** cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面文件中的[Get-csexumcontact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 。</span><span class="sxs-lookup"><span data-stu-id="9305d-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

