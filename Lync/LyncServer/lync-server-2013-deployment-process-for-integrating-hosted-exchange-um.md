---
title: Lync Server 2013： 部署程序的整合主控 Exchange UM
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
ms.openlocfilehash: cdab3e470037780d871f9ac6a5eba549497cd23a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="30073-102">部署程序的整合主控 Exchange UM 與 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30073-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30073-103">_**主題上次修改日期：** 2012年-09-25_</span><span class="sxs-lookup"><span data-stu-id="30073-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="30073-104">整合 Lync Server 2013 與裝載 Exchange 整合通訊 (UM) 的有效地規劃，需要考慮下列：</span><span class="sxs-lookup"><span data-stu-id="30073-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="30073-105">與裝載 Exchange UM 整合 Lync Server 2013 的必要條件</span><span class="sxs-lookup"><span data-stu-id="30073-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="30073-106">整合過程所需的步驟</span><span class="sxs-lookup"><span data-stu-id="30073-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="30073-107">與裝載 Exchange UM 整合的部署先決條件</span><span class="sxs-lookup"><span data-stu-id="30073-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="30073-108">您可以開始整合程序之前，您必須已部署 Lync Server 2013 （在最低限度下，前端集區或 Standard Edition server）、 Edge Server 和 Lync 2013 或 Lync 2010 用戶端。</span><span class="sxs-lookup"><span data-stu-id="30073-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="30073-109">整合程序</span><span class="sxs-lookup"><span data-stu-id="30073-109">Integration Process</span></span>

<span data-ttu-id="30073-110">下表提供主控 Exchange UM 整合程序的概觀。</span><span class="sxs-lookup"><span data-stu-id="30073-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="30073-111">如需部署步驟的詳細資訊，請參閱部署文件中[提供 Lync Server 2013 使用者語音上裝載的 Exchange UM 的信箱](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)。</span><span class="sxs-lookup"><span data-stu-id="30073-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30073-112">階段</span><span class="sxs-lookup"><span data-stu-id="30073-112">Phase</span></span></th>
<th><span data-ttu-id="30073-113">步驟</span><span class="sxs-lookup"><span data-stu-id="30073-113">Steps</span></span></th>
<th><span data-ttu-id="30073-114">權利和權限</span><span class="sxs-lookup"><span data-stu-id="30073-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="30073-115">部署文件</span><span class="sxs-lookup"><span data-stu-id="30073-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30073-116">設定 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="30073-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="30073-117">設定同盟的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="30073-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="30073-118">以手動方式將資料複寫至 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="30073-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="30073-119">在 Edge Server 上設定裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="30073-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="30073-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="30073-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="30073-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">設定 Edge Server 進行整合與裝載 Exchange UM</a></span><span class="sxs-lookup"><span data-stu-id="30073-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30073-122">設定裝載的語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="30073-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="30073-123">修改全域裝載的語音信箱原則或是網站或個別使用者範圍建立新的裝載的語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="30073-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="30073-124">針對每個使用者範圍的原則，請將原則指派給使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="30073-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="30073-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="30073-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="30073-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">管理 Lync Server 2013 中的主控的語音信箱原則</a></span><span class="sxs-lookup"><span data-stu-id="30073-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30073-127">啟用使用者的主控的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="30073-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="30073-128">設定使用者信箱位於裝載 Exchange 服務上的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="30073-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="30073-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="30073-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="30073-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">啟用使用者的 Lync Server 2013 中裝載的語音信箱</a></span><span class="sxs-lookup"><span data-stu-id="30073-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30073-131">設定裝載連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="30073-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="30073-132">為裝載的 Exchange UM 建立自動語音應答連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="30073-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="30073-133">為裝載的 Exchange UM 建立訂戶存取連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="30073-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="30073-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="30073-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="30073-135">若要建立、 修改或移除連絡人物件，執行 New-csexumcontact，使用者 Set-csexumcontact 或移除 Get-csexumcontact cmdlet 必須正確的權限，以儲存新的連絡人物件所在的 Active Directory 組織單位。</span><span class="sxs-lookup"><span data-stu-id="30073-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="30073-136">執行 Grant-CsOUPermission Cmdlet，即可授與此權限。</span><span class="sxs-lookup"><span data-stu-id="30073-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="30073-137">如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。</span><span class="sxs-lookup"><span data-stu-id="30073-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="30073-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">為裝載的 Exchange UM Lync Server 2013 中建立連絡人物件</a></span><span class="sxs-lookup"><span data-stu-id="30073-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

