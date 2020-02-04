---
title: 確認所有 Exchange UM 連絡人物件都已從舊版池中移除
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
ms.openlocfilehash: 0e49aa2fdef3731a34de05e04b8195cb8aa32cd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="d71c1-102">確認所有 Exchange UM 連絡人物件都已從舊版池中移除</span><span class="sxs-lookup"><span data-stu-id="d71c1-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d71c1-103">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="d71c1-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="d71c1-104">使用**OCSUmUtil**工具或**CsExumContact** CMDLET，確認 Exchange UM 連絡人物件已從舊版 Office 通訊伺服器 2007 R2 池中移除。</span><span class="sxs-lookup"><span data-stu-id="d71c1-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="d71c1-105">**OCSUmUtil**位於下列資料夾中：</span><span class="sxs-lookup"><span data-stu-id="d71c1-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="d71c1-106">% Program Files%\\常見檔案\\Lync Server 2013\\支援\\OcsUMUtil</span><span class="sxs-lookup"><span data-stu-id="d71c1-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="d71c1-107">**OCSUmUtil**必須從具有下列專案的使用者帳戶執行：</span><span class="sxs-lookup"><span data-stu-id="d71c1-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="d71c1-108">RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 群組中的成員資格（包含讀取 Exchange Server 整合通訊設定的許可權）</span><span class="sxs-lookup"><span data-stu-id="d71c1-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="d71c1-109">在指定組織單位（OU）容器中建立連絡人物件的網域權利</span><span class="sxs-lookup"><span data-stu-id="d71c1-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="d71c1-110">如需有關使用**CsExumContact** Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔中的[CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 。</span><span class="sxs-lookup"><span data-stu-id="d71c1-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

