---
title: Lync Server 2013：整合主控 Exchange UM 的部署程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b314ea3bd7a88264a72c804c7c67ed3baa819972
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="b3146-102">整合主控 Exchange UM 和 Lync Server 2013 的部署程序</span><span class="sxs-lookup"><span data-stu-id="b3146-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3146-103">_**主題上次修改日期：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="b3146-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="b3146-104">整合 Lync Server 2013 與託管 Exchange 整合訊息（UM）的有效規劃，必須考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="b3146-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="b3146-105">整合 Lync Server 2013 與託管 Exchange UM 的先決條件</span><span class="sxs-lookup"><span data-stu-id="b3146-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="b3146-106">整合過程中所需的步驟</span><span class="sxs-lookup"><span data-stu-id="b3146-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="b3146-107">與託管 Exchange UM 整合的部署先決條件</span><span class="sxs-lookup"><span data-stu-id="b3146-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="b3146-108">您必須已部署 Lync Server 2013 （至少是前端池或標準版伺服器）、邊緣伺服器以及 Lync 2013 或 Lync 2010 用戶端，才能開始整合程式。</span><span class="sxs-lookup"><span data-stu-id="b3146-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="b3146-109">整合程式</span><span class="sxs-lookup"><span data-stu-id="b3146-109">Integration Process</span></span>

<span data-ttu-id="b3146-110">下表提供託管 Exchange UM 整合程式的概覽。</span><span class="sxs-lookup"><span data-stu-id="b3146-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="b3146-111">如需部署步驟的詳細資訊，請參閱在部署檔中[提供 Lync Server 2013 使用者 [託管 EXCHANGE UM] 上的語音信箱](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)。</span><span class="sxs-lookup"><span data-stu-id="b3146-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3146-112">分</span><span class="sxs-lookup"><span data-stu-id="b3146-112">Phase</span></span></th>
<th><span data-ttu-id="b3146-113">步驟</span><span class="sxs-lookup"><span data-stu-id="b3146-113">Steps</span></span></th>
<th><span data-ttu-id="b3146-114">權利和許可權</span><span class="sxs-lookup"><span data-stu-id="b3146-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="b3146-115">部署檔</span><span class="sxs-lookup"><span data-stu-id="b3146-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3146-116">設定邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="b3146-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b3146-117">設定同盟的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="b3146-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="b3146-118">手動將資料複製到 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b3146-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="b3146-119">在 Edge 伺服器上設定主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="b3146-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b3146-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b3146-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="b3146-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">將 Edge Server 設定為與主控 Exchange UM 整合</a></span><span class="sxs-lookup"><span data-stu-id="b3146-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3146-122">設定託管的語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="b3146-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b3146-123">您可以修改全域託管的語音信箱原則，或建立新的託管語音信箱原則，以及網站或每個使用者的範圍。</span><span class="sxs-lookup"><span data-stu-id="b3146-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="b3146-124">針對每個使用者範圍的原則，將原則指派給 [使用者] 或 [群組]。</span><span class="sxs-lookup"><span data-stu-id="b3146-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b3146-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b3146-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="b3146-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">在 Lync Server 2013 中管理裝載語音信箱原則</a></span><span class="sxs-lookup"><span data-stu-id="b3146-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3146-127">允許使用者使用託管的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b3146-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b3146-128">針對其信箱位於託管 Exchange 服務的使用者，設定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b3146-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b3146-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b3146-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="b3146-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">在 Lync Server 2013 中為使用者啟用主控語音信箱</a></span><span class="sxs-lookup"><span data-stu-id="b3146-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3146-131">設定託管連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="b3146-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b3146-132">建立託管 Exchange UM 的自動助理連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="b3146-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="b3146-133">針對託管 Exchange UM 建立訂閱者存取連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="b3146-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b3146-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b3146-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b3146-135">若要建立、修改或移除連絡人物件，執行新的 CsExUmContact、Set CsExUmContact 或 Remove CsExUmContact Cmdlet 的使用者必須具備儲存新連絡人物件之 Active Directory 組織單位的正確許可權。</span><span class="sxs-lookup"><span data-stu-id="b3146-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="b3146-136">您可以執行授與 CsOUPermission Cmdlet 來授與此許可權。</span><span class="sxs-lookup"><span data-stu-id="b3146-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="b3146-137">如需詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="b3146-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="b3146-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">在 Lync Server 2013 中建立主控 Exchange UM 的聯絡人物件</a></span><span class="sxs-lookup"><span data-stu-id="b3146-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

