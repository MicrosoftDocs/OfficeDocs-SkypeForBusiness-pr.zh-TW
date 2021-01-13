---
title: 商務用 Skype Server 控制台的第一次執行檢查清單
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 歡迎使用商務用 Skype Server 控制台，以 web 為基礎的使用者介面，用來管理和管理商務用 Skype Server。 您可以使用 [控制台] 執行先前版本中使用 Microsoft 管理主控台所執行的系統管理工作類型。
ms.openlocfilehash: 74c1d4ae7b9ed65932acf5b8491a2cd00c67831c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804893"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a><span data-ttu-id="05803-104">商務用 Skype Server 控制台的第一次執行檢查清單</span><span class="sxs-lookup"><span data-stu-id="05803-104">First Run Checklist for Skype for Business Server Control Panel</span></span>

<span data-ttu-id="05803-105">歡迎使用商務用 Skype Server 控制台，以 web 為基礎的使用者介面，用來管理和管理商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="05803-105">Welcome to the Skype for Business Server Control Panel, the web-based user interface for administration and management of Skype for Business Server.</span></span> <span data-ttu-id="05803-106">您可以使用 [控制台] 執行先前版本中使用 Microsoft 管理主控台所執行的系統管理工作類型。</span><span class="sxs-lookup"><span data-stu-id="05803-106">You can use the control panel to perform the types of administrative tasks that were performed for by using the Microsoft Management Console in previous releases.</span></span>

<span data-ttu-id="05803-107">在您部署商務用 Skype Server 之後，我們強烈建議您執行一些重要工作。</span><span class="sxs-lookup"><span data-stu-id="05803-107">There are a number of important tasks that we strongly recommend you perform after you have deployed Skype for Business Server.</span></span> <span data-ttu-id="05803-108">這些工作中，一部份是初始設定步驟，您可能已在部署期間執行過，但其他的則是針對您在部署期間的設定或是預設設定進行細分或修改。</span><span class="sxs-lookup"><span data-stu-id="05803-108">Some of these tasks are initial configuration steps that you may have already performed during deployment, while others are refinements or modifications to settings that you configured during deployment or default settings.</span></span> <span data-ttu-id="05803-109">本主題中描述的其他工作會驗證您在部署過程中所進行的設定。</span><span class="sxs-lookup"><span data-stu-id="05803-109">Other tasks described in this topic validate the configurations you made during the deployment process.</span></span>

> [!NOTE]
> <span data-ttu-id="05803-110">在執行下表中的工作之前，請務必使用「 [Role-Based 存取控制](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) 」主題中的「角色與範圍」一節所述的正確使用者權限、許可權和角色進行登入。</span><span class="sxs-lookup"><span data-stu-id="05803-110">Before performing the tasks in the following table, ensure that you log on using the correct user rights, permissions, and role as described in the "Roles and Scope" section of the [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) topic.</span></span>

## <a name="first-run-checklist"></a><span data-ttu-id="05803-111">第一次執行檢查清單</span><span class="sxs-lookup"><span data-stu-id="05803-111">First Run Checklist</span></span>

<span data-ttu-id="05803-112">強烈建議您複查本主題中所述的工作，然後針對組織中的 Lync Server 部署執行適當的程式。</span><span class="sxs-lookup"><span data-stu-id="05803-112">We strongly recommend that you review the tasks referred to in this topic, and then perform the appropriate procedures for the Lync Server deployment in your organization.</span></span>

|<span data-ttu-id="05803-113">**工作**</span><span class="sxs-lookup"><span data-stu-id="05803-113">**Task**</span></span>|<span data-ttu-id="05803-114">**控制台群組**</span><span class="sxs-lookup"><span data-stu-id="05803-114">**Control Panel group**</span></span>|<span data-ttu-id="05803-115">**文件**</span><span class="sxs-lookup"><span data-stu-id="05803-115">**Documentation**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="05803-116">確認您安裝在拓撲中的服務如預期地執行中。</span><span class="sxs-lookup"><span data-stu-id="05803-116">Verify the services that you installed in your topology are running as expected.</span></span>  <br/> |<span data-ttu-id="05803-117">**拓撲**</span><span class="sxs-lookup"><span data-stu-id="05803-117">**Topology**</span></span> <br/> |[<span data-ttu-id="05803-118">查看服務的詳細資料</span><span class="sxs-lookup"><span data-stu-id="05803-118">View Details About a Service</span></span>](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|<span data-ttu-id="05803-119">為使用者啟用商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="05803-119">Enable users for Skype for Business Server.</span></span> <span data-ttu-id="05803-120">（選用）從先前版本遷移時，將使用者移至商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="05803-120">Optionally and, if migrating from a previous release, move users to Skype for Business Server.</span></span>  <br/> |<span data-ttu-id="05803-121">**使用者**</span><span class="sxs-lookup"><span data-stu-id="05803-121">**Users**</span></span> <br/> |[<span data-ttu-id="05803-122">管理使用者</span><span class="sxs-lookup"><span data-stu-id="05803-122">Managing Users</span></span>](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|<span data-ttu-id="05803-123">如果您已部署，或想要部署 Enterprise Voice，請設定 SIP 主幹連線，以啟用對公用交換電話網路 (PSTN) 的連線。</span><span class="sxs-lookup"><span data-stu-id="05803-123">If you deployed or want to deploy Enterprise Voice, configure a SIP trunk connection to enable connectivity to the public switched telephone network (PSTN).</span></span>  <br/> |<span data-ttu-id="05803-124">**語音路由**</span><span class="sxs-lookup"><span data-stu-id="05803-124">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="05803-125">設定主幹和轉譯規則</span><span class="sxs-lookup"><span data-stu-id="05803-125">Configuring Trunks and Translation Rules</span></span>](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|<span data-ttu-id="05803-126">如果您部署了 Enterprise Voice，請確認 Enterprise Voice 路由設定。</span><span class="sxs-lookup"><span data-stu-id="05803-126">If you deployed Enterprise Voice, verify Enterprise Voice routing settings.</span></span>  <br/> |<span data-ttu-id="05803-127">**語音路由**</span><span class="sxs-lookup"><span data-stu-id="05803-127">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="05803-128">測試語音路由</span><span class="sxs-lookup"><span data-stu-id="05803-128">Test Voice Routing</span></span>](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|<span data-ttu-id="05803-129">如果您部署了封存伺服器，請確認封存原則和設定符合您組織的規範需要。</span><span class="sxs-lookup"><span data-stu-id="05803-129">If you deployed Archiving Server, verify that archiving policies and settings meet the compliance needs of your organization.</span></span>  <br/> |<span data-ttu-id="05803-130">**監控和封存**</span><span class="sxs-lookup"><span data-stu-id="05803-130">**Monitoring and Archiving**</span></span> <br/> |[<span data-ttu-id="05803-131">管理封存</span><span class="sxs-lookup"><span data-stu-id="05803-131">Managing Archiving</span></span>](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|<span data-ttu-id="05803-132">如果您部署了監控伺服器，請檢視監控伺服器報告，以便檢視使用方式和診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="05803-132">If you deployed Monitoring Server, view Monitoring Server reports to view usage and diagnostic information.</span></span>  <br/> |<span data-ttu-id="05803-133">**首頁**</span><span class="sxs-lookup"><span data-stu-id="05803-133">**Home**</span></span> <br/> |[<span data-ttu-id="05803-134">在商務用 Skype Server 2015 中管理健康情況與監控</span><span class="sxs-lookup"><span data-stu-id="05803-134">Manage health and monitoring in Skype for Business Server 2015</span></span>](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


