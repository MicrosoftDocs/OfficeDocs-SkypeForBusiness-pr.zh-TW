---
title: Skype for Busines 應力和效能工具的必要條件和設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: 商務用 Skype Server 2015 應力和效能工具的需求或必要條件。 如何安裝或設定壓力和效能工具。
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814953"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="3026a-104">Skype for Busines 應力和效能工具的必要條件和設定</span><span class="sxs-lookup"><span data-stu-id="3026a-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="3026a-105">商務用 Skype Server 2015 應力和效能工具的需求或必要條件。</span><span class="sxs-lookup"><span data-stu-id="3026a-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="3026a-106">如何安裝或設定壓力和效能工具。</span><span class="sxs-lookup"><span data-stu-id="3026a-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="3026a-107">在執行壓力和效能工具之前，我們有下列幾節需要注意的硬體、軟體和系統設定需求：</span><span class="sxs-lookup"><span data-stu-id="3026a-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="3026a-108">用戶端硬體需求</span><span class="sxs-lookup"><span data-stu-id="3026a-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="3026a-109">用戶端軟體需求</span><span class="sxs-lookup"><span data-stu-id="3026a-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="3026a-110">設定需求</span><span class="sxs-lookup"><span data-stu-id="3026a-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="3026a-111">此外，我們還提供下列章節，以供 [安裝商務用 Skype Server 2015 應力和效能工具](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="3026a-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="3026a-112">用戶端硬體需求</span><span class="sxs-lookup"><span data-stu-id="3026a-112">Client hardware requirements</span></span>
<span data-ttu-id="3026a-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="3026a-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="3026a-114">針對您的商務用 Skype Server 2015 部署執行壓力和效能工具時，您至少需要滿足測試中每個4500使用者的下列硬體需求：</span><span class="sxs-lookup"><span data-stu-id="3026a-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="3026a-115">1 gb 網路介面卡</span><span class="sxs-lookup"><span data-stu-id="3026a-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="3026a-116">8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="3026a-116">8 GB RAM</span></span>
    
- <span data-ttu-id="3026a-117">2顆雙核 CPUs</span><span class="sxs-lookup"><span data-stu-id="3026a-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="3026a-118">用戶端軟體需求</span><span class="sxs-lookup"><span data-stu-id="3026a-118">Client software requirements</span></span>
<span data-ttu-id="3026a-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="3026a-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="3026a-120">壓力和效能工具支援的作業系統如下：</span><span class="sxs-lookup"><span data-stu-id="3026a-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="3026a-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="3026a-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="3026a-122">Windows Server 2008 (64-位) </span><span class="sxs-lookup"><span data-stu-id="3026a-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="3026a-123">此外，電腦必須滿足下列軟體需求：</span><span class="sxs-lookup"><span data-stu-id="3026a-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="3026a-124">您將需要安裝 Microsoft .NET 4.5 Framework。</span><span class="sxs-lookup"><span data-stu-id="3026a-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="3026a-125">在這裡下載 .Net 4.5 Framework。</span><span class="sxs-lookup"><span data-stu-id="3026a-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="3026a-126">您將需要 Windows 中啟用的桌面體驗功能。</span><span class="sxs-lookup"><span data-stu-id="3026a-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="3026a-127">您將需要安裝 Microsoft Visual c + + 2013 (x64) 。</span><span class="sxs-lookup"><span data-stu-id="3026a-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="3026a-128">在這裡下載 Visual c + + 2013</span><span class="sxs-lookup"><span data-stu-id="3026a-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="3026a-129">您即將成功部署商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="3026a-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="3026a-130">設定需求</span><span class="sxs-lookup"><span data-stu-id="3026a-130">Configuration requirements</span></span>
<span data-ttu-id="3026a-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="3026a-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="3026a-132">您將需要進行下列額外設定，以順利執行壓力和效能工具：</span><span class="sxs-lookup"><span data-stu-id="3026a-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="3026a-133">您必須以網域或本機管理員群組成員的身分登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="3026a-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="3026a-134">您無法在使用者帳戶所在的任何前端伺服器或 Standard Edition server 上安裝商務用 Skype Server 2015 使用者建立工具 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="3026a-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="3026a-135">當使用者建立工具多次執行時，每個啟用 Microsoft 整合通訊的使用者都必須有唯一的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3026a-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="3026a-136">頁面檔案大小應是系統管理的，否則至少必須是電腦系統中 RAM 的記憶體量的1.5 倍。</span><span class="sxs-lookup"><span data-stu-id="3026a-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="3026a-137">安裝商務用 Skype Server 2015 應力和效能工具</span><span class="sxs-lookup"><span data-stu-id="3026a-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="3026a-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="3026a-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="3026a-139">安裝會變得更簡單。</span><span class="sxs-lookup"><span data-stu-id="3026a-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="3026a-140">您必須在您要用來模擬使用者流量的每一部用戶端電腦上，，在您要建立使用者和連絡人的每個集區的前端伺服器上執行 Windows Installer 檔案（ **CapacityPlanningTool.msi**）。</span><span class="sxs-lookup"><span data-stu-id="3026a-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="3026a-141">若要下載 .msi，以及其他文章中提及的範例腳本，請移至 [下載中心] 連結：商務用 [Skype Server 2015、壓力和效能工具](https://www.microsoft.com/download/details.aspx?id=50367)。</span><span class="sxs-lookup"><span data-stu-id="3026a-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

