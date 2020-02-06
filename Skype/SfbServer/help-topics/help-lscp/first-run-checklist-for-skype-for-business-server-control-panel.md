---
title: 商務用 Skype Server 控制台的初次執行檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: 歡迎使用商務用 Skype Server 的 [控制台]，它是用來管理和管理商務用 Skype Server 的 web 使用者介面。 您可以使用控制台來執行過去只能透過 Microsoft 管理主控台執行的管理工作類型。
ms.openlocfilehash: 05fb040a683b81ae2b9b36c6018f7e52ef93d58f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822766"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a><span data-ttu-id="6b272-104">商務用 Skype Server 控制台的初次執行檢查清單</span><span class="sxs-lookup"><span data-stu-id="6b272-104">First Run Checklist for Skype for Business Server Control Panel</span></span>

<span data-ttu-id="6b272-105">歡迎使用商務用 Skype Server 的 [控制台]，它是用來管理和管理商務用 Skype Server 的 web 使用者介面。</span><span class="sxs-lookup"><span data-stu-id="6b272-105">Welcome to the Skype for Business Server Control Panel, the web-based user interface for administration and management of Skype for Business Server.</span></span> <span data-ttu-id="6b272-106">您可以使用控制台來執行過去只能透過 Microsoft 管理主控台執行的管理工作類型。</span><span class="sxs-lookup"><span data-stu-id="6b272-106">You can use the control panel to perform the types of administrative tasks that were performed for by using the Microsoft Management Console in previous releases.</span></span>

<span data-ttu-id="6b272-107">在您部署商務用 Skype Server 之後，我們強烈建議您執行一些重要的工作。</span><span class="sxs-lookup"><span data-stu-id="6b272-107">There are a number of important tasks that we strongly recommend you perform after you have deployed Skype for Business Server.</span></span> <span data-ttu-id="6b272-108">這些工作包含您可能在部署期間已執行過的初始設定步驟，其他則是針對您在部署期間的設定或預設值進行細分或修改。</span><span class="sxs-lookup"><span data-stu-id="6b272-108">Some of these tasks are initial configuration steps that you may have already performed during deployment, while others are refinements or modifications to settings that you configured during deployment or default settings.</span></span> <span data-ttu-id="6b272-109">本主題中描述的其他工作會驗證您在部署過程中所進行的設定。</span><span class="sxs-lookup"><span data-stu-id="6b272-109">Other tasks described in this topic validate the configurations you made during the deployment process.</span></span>

> [!NOTE]
> <span data-ttu-id="6b272-110">在開始執行下表中的工作之前，請確認您行使正確的使用者權利與權限，並以適當的角色登入，如同〈[Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)〉的〈角色和範圍〉一節的描述。</span><span class="sxs-lookup"><span data-stu-id="6b272-110">Before performing the tasks in the following table, ensure that you log on using the correct user rights, permissions, and role as described in the "Roles and Scope" section of the [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) topic.</span></span>

## <a name="first-run-checklist"></a><span data-ttu-id="6b272-111">第一次執行檢查清單</span><span class="sxs-lookup"><span data-stu-id="6b272-111">First Run Checklist</span></span>

<span data-ttu-id="6b272-112">我們強烈建議您複習本主題中提到的工作，然後針對貴組織中的 Lync Server 部署執行適當的程式。</span><span class="sxs-lookup"><span data-stu-id="6b272-112">We strongly recommend that you review the tasks referred to in this topic, and then perform the appropriate procedures for the Lync Server deployment in your organization.</span></span>

|<span data-ttu-id="6b272-113">**工作**</span><span class="sxs-lookup"><span data-stu-id="6b272-113">**Task**</span></span>|<span data-ttu-id="6b272-114">**控制台群組**</span><span class="sxs-lookup"><span data-stu-id="6b272-114">**Control Panel group**</span></span>|<span data-ttu-id="6b272-115">**文件**</span><span class="sxs-lookup"><span data-stu-id="6b272-115">**Documentation**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6b272-116">確認您安裝在拓撲中的服務如預期地執行中。</span><span class="sxs-lookup"><span data-stu-id="6b272-116">Verify the services that you installed in your topology are running as expected.</span></span>  <br/> |<span data-ttu-id="6b272-117">**拓撲**</span><span class="sxs-lookup"><span data-stu-id="6b272-117">**Topology**</span></span> <br/> |[<span data-ttu-id="6b272-118">View Details About a Service</span><span class="sxs-lookup"><span data-stu-id="6b272-118">View Details About a Service</span></span>](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|<span data-ttu-id="6b272-119">針對商務用 Skype Server 啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="6b272-119">Enable users for Skype for Business Server.</span></span> <span data-ttu-id="6b272-120">或者，如果從舊版遷移，請將使用者移至商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="6b272-120">Optionally and, if migrating from a previous release, move users to Skype for Business Server.</span></span>  <br/> |<span data-ttu-id="6b272-121">**使用者**</span><span class="sxs-lookup"><span data-stu-id="6b272-121">**Users**</span></span> <br/> |[<span data-ttu-id="6b272-122">Managing Users</span><span class="sxs-lookup"><span data-stu-id="6b272-122">Managing Users</span></span>](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|<span data-ttu-id="6b272-123">如果您已部署，或想要部署企業語音，請設定 SIP 主幹連線，以啟用對公用交換電話網路 (PSTN) 的連線。</span><span class="sxs-lookup"><span data-stu-id="6b272-123">If you deployed or want to deploy Enterprise Voice, configure a SIP trunk connection to enable connectivity to the public switched telephone network (PSTN).</span></span>  <br/> |<span data-ttu-id="6b272-124">**語音路由**</span><span class="sxs-lookup"><span data-stu-id="6b272-124">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="6b272-125">Configuring Trunks and Translation Rules</span><span class="sxs-lookup"><span data-stu-id="6b272-125">Configuring Trunks and Translation Rules</span></span>](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|<span data-ttu-id="6b272-126">如果您部署了企業語音，請確認企業語音路由設定。</span><span class="sxs-lookup"><span data-stu-id="6b272-126">If you deployed Enterprise Voice, verify Enterprise Voice routing settings.</span></span>  <br/> |<span data-ttu-id="6b272-127">**語音路由**</span><span class="sxs-lookup"><span data-stu-id="6b272-127">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="6b272-128">Test Voice Routing</span><span class="sxs-lookup"><span data-stu-id="6b272-128">Test Voice Routing</span></span>](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|<span data-ttu-id="6b272-129">如果您部署了封存伺服器，請確認封存原則和設定符合您組織的規範需要。</span><span class="sxs-lookup"><span data-stu-id="6b272-129">If you deployed Archiving Server, verify that archiving policies and settings meet the compliance needs of your organization.</span></span>  <br/> |<span data-ttu-id="6b272-130">**監控和封存**</span><span class="sxs-lookup"><span data-stu-id="6b272-130">**Monitoring and Archiving**</span></span> <br/> |[<span data-ttu-id="6b272-131">Managing Archiving</span><span class="sxs-lookup"><span data-stu-id="6b272-131">Managing Archiving</span></span>](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|<span data-ttu-id="6b272-132">如果您部署了監控伺服器，請檢視監控伺服器報告，以便檢視使用方式和診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="6b272-132">If you deployed Monitoring Server, view Monitoring Server reports to view usage and diagnostic information.</span></span>  <br/> |<span data-ttu-id="6b272-133">**首頁**</span><span class="sxs-lookup"><span data-stu-id="6b272-133">**Home**</span></span> <br/> |[<span data-ttu-id="6b272-134">在商務用 Skype 中管理運作狀況與監控</span><span class="sxs-lookup"><span data-stu-id="6b272-134">Manage health and monitoring in Skype for Business Server 2015</span></span>](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


