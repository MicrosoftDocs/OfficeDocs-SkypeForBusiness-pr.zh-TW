---
title: Lync Server 2013：整合主控 Exchange UM 的部署程式
description: Lync Server 2013：整合主控 Exchange UM 的部署程式。
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
ms.openlocfilehash: 83239c6534dfdaa65109c8880cc4cb4946bffab6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542609"
---
# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="7f4cf-103">整合主控 Exchange UM 與 Lync Server 2013 的部署程式</span><span class="sxs-lookup"><span data-stu-id="7f4cf-103">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f4cf-104">_**主題上次修改日期：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="7f4cf-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="7f4cf-105">若要有效規劃整合 Lync Server 2013 與主控 Exchange 整合通訊 (UM) ，必須考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="7f4cf-105">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="7f4cf-106">整合 Lync Server 2013 與主控 Exchange UM 的必要條件</span><span class="sxs-lookup"><span data-stu-id="7f4cf-106">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="7f4cf-107">整合過程中所需的步驟</span><span class="sxs-lookup"><span data-stu-id="7f4cf-107">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="7f4cf-108">與主控 Exchange UM 整合的部署必要條件</span><span class="sxs-lookup"><span data-stu-id="7f4cf-108">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="7f4cf-109">在您開始進行整合程式之前，您必須已部署 Lync Server 2013 (，至少要有一個前端集區或 Standard Edition server) 、Edge Server，以及 Lync 2013 或 Lync 2010 用戶端。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-109">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="7f4cf-110">整合處理常式</span><span class="sxs-lookup"><span data-stu-id="7f4cf-110">Integration Process</span></span>

<span data-ttu-id="7f4cf-111">下表提供主控 Exchange UM 整合處理常式的概述。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-111">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="7f4cf-112">如需部署步驟的詳細資訊，請參閱部署檔中的在 [主控 EXCHANGE UM 上提供 Lync Server 2013 使用者語音信箱](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) 。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-112">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f4cf-113">階段</span><span class="sxs-lookup"><span data-stu-id="7f4cf-113">Phase</span></span></th>
<th><span data-ttu-id="7f4cf-114">步驟</span><span class="sxs-lookup"><span data-stu-id="7f4cf-114">Steps</span></span></th>
<th><span data-ttu-id="7f4cf-115">權利和許可權</span><span class="sxs-lookup"><span data-stu-id="7f4cf-115">Rights and permissions</span></span></th>
<th><span data-ttu-id="7f4cf-116">部署文件</span><span class="sxs-lookup"><span data-stu-id="7f4cf-116">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f4cf-117">設定 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-117">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7f4cf-118">設定同盟的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-118">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="7f4cf-119">手動將資料複製到 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-119">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="7f4cf-120">在 Edge Server 上設定裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-120">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7f4cf-121">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7f4cf-121">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7f4cf-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">將 Edge Server 設定為與主控 Exchange UM 整合</a></span><span class="sxs-lookup"><span data-stu-id="7f4cf-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f4cf-123">設定主控語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-123">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7f4cf-124">請修改全域裝載語音信箱原則，或使用網站或 Per-User 範圍建立新的主控語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-124">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="7f4cf-125">針對 Per-User 範圍的原則，將原則指派給使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-125">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7f4cf-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7f4cf-126">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7f4cf-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">在 Lync Server 2013 中管理主控語音信箱原則</a></span><span class="sxs-lookup"><span data-stu-id="7f4cf-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f4cf-128">為使用者啟用主控語音信箱。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-128">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7f4cf-129">為信箱在主控 Exchange 服務上的使用者設定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-129">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7f4cf-130">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7f4cf-130">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="7f4cf-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">在 Lync Server 2013 中啟用使用者的主控語音信箱功能</a></span><span class="sxs-lookup"><span data-stu-id="7f4cf-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f4cf-132">設定主控的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-132">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7f4cf-133">為主控 Exchange UM 建立自動語音應答連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-133">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="7f4cf-134">建立主控 Exchange UM 的訂戶存取連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-134">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7f4cf-135">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7f4cf-135">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7f4cf-136">若要建立、修改或移除連絡人物件，執行 New-CsExUmContact 的使用者、Set-CsExUmContact 或 Remove-CsExUmContact Cmdlet 必須具有儲存新連絡人物件之 Active Directory 組織單位的適當許可權。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-136">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="7f4cf-137">執行 Grant-CsOUPermission Cmdlet，即可授與此權限。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-137">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="7f4cf-138">如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。</span><span class="sxs-lookup"><span data-stu-id="7f4cf-138">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="7f4cf-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">在 Lync Server 2013 中建立主控 Exchange UM 的連絡人物件</a></span><span class="sxs-lookup"><span data-stu-id="7f4cf-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

