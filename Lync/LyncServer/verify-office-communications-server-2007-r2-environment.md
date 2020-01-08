---
title: 驗證 Office Communications Server 2007 R2 環境
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9369ad631b772e0a73677ab3214e24083426148a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="49c3a-102">驗證 Office Communications Server 2007 R2 環境</span><span class="sxs-lookup"><span data-stu-id="49c3a-102">Verify Office Communications Server 2007 R2 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49c3a-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="49c3a-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="49c3a-104">在使用 Office 通訊伺服器 2007 R2 的共存狀態中部署 Lync Server 2013 之前，您必須確認 Office 通訊伺服器 2007 R2 服務已設定並啟動。</span><span class="sxs-lookup"><span data-stu-id="49c3a-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="49c3a-105">**驗證已使用 Office 通訊伺服器 2007 R2 管理工具啟動該池**</span><span class="sxs-lookup"><span data-stu-id="49c3a-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="49c3a-106">開啟 Office 通訊伺服器 2007 R2 管理工具。</span><span class="sxs-lookup"><span data-stu-id="49c3a-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="49c3a-107">展開 [**目錄林**] 節點，展開 [**標準版伺服器**] 或 [**企業版池**] 節點，然後展開 [池] 或 [伺服器名稱]。</span><span class="sxs-lookup"><span data-stu-id="49c3a-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="49c3a-108">確定服務正在標準版伺服器或企業版池上執行。</span><span class="sxs-lookup"><span data-stu-id="49c3a-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="49c3a-109">![Office 通訊伺服器 2007 R2 管理主控台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "office 通訊伺服器 2007 R2 系統管理主控台")</span><span class="sxs-lookup"><span data-stu-id="49c3a-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="49c3a-110">**審查針對 Office 通訊伺服器 2007 R2 設定的使用者**</span><span class="sxs-lookup"><span data-stu-id="49c3a-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="49c3a-111">開啟 Office 通訊伺服器 2007 R2 管理工具。</span><span class="sxs-lookup"><span data-stu-id="49c3a-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="49c3a-112">展開 [**目錄林**] 節點，展開 [**標準版伺服器**] 或 [**企業版池**] 節點，然後展開 [池] 或 [伺服器名稱]。</span><span class="sxs-lookup"><span data-stu-id="49c3a-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="49c3a-113">按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="49c3a-113">Click **Users**.</span></span>

4.  <span data-ttu-id="49c3a-114">驗證 Office 通訊伺服器 2007 R2 使用者的清單。</span><span class="sxs-lookup"><span data-stu-id="49c3a-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="49c3a-115">在(images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Ocs 管理工具")中的 [ocs 管理工具清單 fo 使用者]![中的使用者清單]</span><span class="sxs-lookup"><span data-stu-id="49c3a-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="49c3a-116">**驗證舊版 XMPP 聯盟合作夥伴設定**</span><span class="sxs-lookup"><span data-stu-id="49c3a-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="49c3a-117">從舊版 XMPP 伺服器流覽至 [管理工具\\服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="49c3a-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="49c3a-118">確認已啟動 Office 通訊伺服器 XMPP 閘道服務。</span><span class="sxs-lookup"><span data-stu-id="49c3a-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="49c3a-119">![Office 通訊伺服器 XMPP 閘道服務](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "OFFICE 通訊伺服器 XMPP 閘道服務")</span><span class="sxs-lookup"><span data-stu-id="49c3a-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

