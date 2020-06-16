---
title: 驗證 Office 通訊伺服器 2007 R2 環境
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14a7ba7e51e6dd1f6e42aeddfbbbd4ce7581d3fc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="6bd27-102">驗證 Office 通訊伺服器 2007 R2 環境</span><span class="sxs-lookup"><span data-stu-id="6bd27-102">Verify Office Communications Server 2007 R2 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bd27-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="6bd27-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="6bd27-104">在使用 Office 通訊伺服器 2007 R2 在共存狀態中部署 Lync Server 2013 之前，您必須確認已設定並啟動 Office 通訊伺服器 2007 R2 服務。</span><span class="sxs-lookup"><span data-stu-id="6bd27-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="6bd27-105">**驗證是否已使用 Office 通訊伺服器 2007 R2 系統管理工具啟動集區**</span><span class="sxs-lookup"><span data-stu-id="6bd27-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="6bd27-106">開啟 Office 通訊伺服器 2007 R2 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="6bd27-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="6bd27-107">依序展開 **[樹系]** 節點及 **[Standard Edition Server]** 或 **[Enterprise Pool]** 節點，然後展開集區或伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="6bd27-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="6bd27-108">確定服務正在 Standard Edition server 或 Enterprise pool 上執行。</span><span class="sxs-lookup"><span data-stu-id="6bd27-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="6bd27-109">![Office 通訊伺服器 2007 R2 管理主控台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office 通訊伺服器 2007 R2 管理主控台")</span><span class="sxs-lookup"><span data-stu-id="6bd27-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="6bd27-110">**檢查針對 Office 通訊伺服器 2007 R2 設定的使用者**</span><span class="sxs-lookup"><span data-stu-id="6bd27-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="6bd27-111">開啟 Office 通訊伺服器 2007 R2 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="6bd27-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="6bd27-112">依序展開 **[樹系]** 節點及 **[Standard Edition Server]** 或 **[Enterprise Pool]** 節點，然後展開集區或伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="6bd27-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="6bd27-113">按一下 [使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6bd27-113">Click **Users**.</span></span>

4.  <span data-ttu-id="6bd27-114">確認 Office 通訊伺服器 2007 R2 使用者的清單。</span><span class="sxs-lookup"><span data-stu-id="6bd27-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="6bd27-115">![OCS 系統管理工具中的使用者清單](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "OCS 系統管理工具中的使用者清單")</span><span class="sxs-lookup"><span data-stu-id="6bd27-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="6bd27-116">**驗證舊版 XMPP 同盟協力廠商設定**</span><span class="sxs-lookup"><span data-stu-id="6bd27-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="6bd27-117">在舊版 XMPP 伺服器上，流覽至 [系統管理工具 \\ 服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="6bd27-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="6bd27-118">確認已啟動 Office 通訊伺服器 XMPP 閘道服務。</span><span class="sxs-lookup"><span data-stu-id="6bd27-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="6bd27-119">![Office 通訊伺服器 XMPP 閘道服務](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office 通訊伺服器 XMPP 閘道服務")</span><span class="sxs-lookup"><span data-stu-id="6bd27-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

