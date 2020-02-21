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

# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="3ee10-102">確認 Office Communications Server 2007 R2 環境</span><span class="sxs-lookup"><span data-stu-id="3ee10-102">Verify Office Communications Server 2007 R2 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ee10-103">_**主題上次修改日期：** 2012 年 10-16_</span><span class="sxs-lookup"><span data-stu-id="3ee10-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="3ee10-104">之前部署處於共存狀態與 Office Communications Server 2007 R2 的 Lync Server 2013，您必須確認 Office Communications Server 2007 R2 服務已設定且啟動。</span><span class="sxs-lookup"><span data-stu-id="3ee10-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="3ee10-105">**確認已啟動集區，使用 Office Communications Server 2007 R2 系統管理工具**</span><span class="sxs-lookup"><span data-stu-id="3ee10-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="3ee10-106">開啟 [Office Communications Server 2007 R2 系統管理工具]。</span><span class="sxs-lookup"><span data-stu-id="3ee10-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="3ee10-107">依序展開 **[樹系]** 節點及 **[Standard Edition Server]** 或 **[Enterprise Pool]** 節點，然後展開集區或伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="3ee10-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="3ee10-108">確定服務執行於 Standard Edition server 或 Enterprise pool。</span><span class="sxs-lookup"><span data-stu-id="3ee10-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="3ee10-109">![Office Communications Server 2007 R2 系統管理主控台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 系統管理主控台")</span><span class="sxs-lookup"><span data-stu-id="3ee10-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="3ee10-110">**檢閱 Office Communications Server 2007 r2 設定的使用者**</span><span class="sxs-lookup"><span data-stu-id="3ee10-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="3ee10-111">開啟 [Office Communications Server 2007 R2 系統管理工具]。</span><span class="sxs-lookup"><span data-stu-id="3ee10-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="3ee10-112">依序展開 **[樹系]** 節點及 **[Standard Edition Server]** 或 **[Enterprise Pool]** 節點，然後展開集區或伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="3ee10-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="3ee10-113">按一下 [使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ee10-113">Click **Users**.</span></span>

4.  <span data-ttu-id="3ee10-114">確認 Office Communications Server 2007 R2 使用者清單。</span><span class="sxs-lookup"><span data-stu-id="3ee10-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="3ee10-115">![NM-OCS-13-2ND 系統管理工具中的清單中的使用者](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "NM-OCS-13-2ND 系統管理工具中的清單中的使用者")</span><span class="sxs-lookup"><span data-stu-id="3ee10-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="3ee10-116">**確認舊版 XMPP 同盟協力廠商設定**</span><span class="sxs-lookup"><span data-stu-id="3ee10-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="3ee10-117">從舊版 XMPP 伺服器瀏覽至系統管理工具\\服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="3ee10-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="3ee10-118">確認 Office Communications Server XMPP 閘道服務已啟動。</span><span class="sxs-lookup"><span data-stu-id="3ee10-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="3ee10-119">![Office Communications Server XMPP 閘道服務](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP 閘道服務")</span><span class="sxs-lookup"><span data-stu-id="3ee10-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

