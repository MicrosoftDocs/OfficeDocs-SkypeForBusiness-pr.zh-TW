---
title: Lync Server 2013： 常設聊天室伺服器資料表詳細資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server table details
ms:assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615034(v=OCS.15)
ms:contentKeyID: 48185323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3caf59185bc3fbe985ea8b7d4371d464b515e3fe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="3c941-102">在 Lync Server 2013 常設聊天室伺服器資料表詳細資料</span><span class="sxs-lookup"><span data-stu-id="3c941-102">Persistent Chat Server table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c941-103">_**主題上次修改日期：** 2012年-06-25_</span><span class="sxs-lookup"><span data-stu-id="3c941-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="3c941-104">下列主題將詳細說明每個常設聊天室資料庫架構表格中的資料行。</span><span class="sxs-lookup"><span data-stu-id="3c941-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3c941-105">本章節內容</span><span class="sxs-lookup"><span data-stu-id="3c941-105">In This Section</span></span>

  - [<span data-ttu-id="3c941-106">Lync Server 2013 中的 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="3c941-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="3c941-107">Lync Server 2013 中的 tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="3c941-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="3c941-108">Lync Server 2013 中的 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="3c941-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="3c941-109">Lync Server 2013 中的 tblprincipalmembers 表格</span><span class="sxs-lookup"><span data-stu-id="3c941-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="3c941-110">Lync Server 2013 中的 tblprincipalmeta 表格</span><span class="sxs-lookup"><span data-stu-id="3c941-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="3c941-111">Lync Server 2013 中的 tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="3c941-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="3c941-112">Lync Server 2013 中的參照 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="3c941-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="3c941-113">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="3c941-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="3c941-114">Lync Server 2013 中的 Principalaffiliations</span><span class="sxs-lookup"><span data-stu-id="3c941-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="3c941-115">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="3c941-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="3c941-116">Lync Server 2013 中的 tblRoleType</span><span class="sxs-lookup"><span data-stu-id="3c941-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="3c941-117">Lync Server 2013 中的 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="3c941-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="3c941-118">Lync Server 2013 中的 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="3c941-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="3c941-119">Lync Server 2013 中的 tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="3c941-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="3c941-120">Lync Server 2013 中的 tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="3c941-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="3c941-121">Lync Server 2013 中的 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="3c941-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="3c941-122">Lync Server 2013 中的 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="3c941-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="3c941-123">Lync Server 2013 中的 tblChat</span><span class="sxs-lookup"><span data-stu-id="3c941-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="3c941-124">Lync Server 2013 中的 tbllastinviteid 表格</span><span class="sxs-lookup"><span data-stu-id="3c941-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="3c941-125">Lync Server 2013 中的 tbllastchatid 表格</span><span class="sxs-lookup"><span data-stu-id="3c941-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="3c941-126">Lync Server 2013 中的 tblPreference</span><span class="sxs-lookup"><span data-stu-id="3c941-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="3c941-127">Lync Server 2013 中的 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="3c941-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="3c941-128">tblServerIdentity 在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c941-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="3c941-129">Lync Server 2013 中的 tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="3c941-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="3c941-130">Lync Server 2013 中的 tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="3c941-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="3c941-131">Lync Server 2013 中的 tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="3c941-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="3c941-132">Lync Server 2013 中的 tblConfig</span><span class="sxs-lookup"><span data-stu-id="3c941-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="3c941-133">Lync Server 2013 中的 tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="3c941-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="3c941-134">Lync Server 2013 中的 tblcompliancefanout 表格</span><span class="sxs-lookup"><span data-stu-id="3c941-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="3c941-135">Lync Server 2013 中的 tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="3c941-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="3c941-136">Lync Server 2013 中的 tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="3c941-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

