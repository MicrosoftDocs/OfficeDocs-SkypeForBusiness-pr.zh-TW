---
title: 必要條件和設定用於商務用 Skype Busines 壓力及效能工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 需求或 Skype for Business Server 2015 壓力及效能工具的必要條件。 如何安裝或設定 [壓力及效能工具。
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005978"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="2a9e5-104">必要條件和設定用於商務用 Skype Busines 壓力及效能工具</span><span class="sxs-lookup"><span data-stu-id="2a9e5-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="2a9e5-105">需求或 Skype for Business Server 2015 壓力及效能工具的必要條件。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="2a9e5-106">如何安裝或設定 [壓力及效能工具。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="2a9e5-107">我們有您需要留意之前執行壓力及效能工具的硬體、 軟體和系統組態需求的下列小節：</span><span class="sxs-lookup"><span data-stu-id="2a9e5-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="2a9e5-108">用戶端的硬體需求</span><span class="sxs-lookup"><span data-stu-id="2a9e5-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="2a9e5-109">用戶端軟體需求</span><span class="sxs-lookup"><span data-stu-id="2a9e5-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="2a9e5-110">組態需求</span><span class="sxs-lookup"><span data-stu-id="2a9e5-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="2a9e5-111">此外，我們也有以下區段[安裝 Skype for Business Server 2015 壓力及效能工具](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="2a9e5-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="2a9e5-112">用戶端的硬體需求</span><span class="sxs-lookup"><span data-stu-id="2a9e5-112">Client hardware requirements</span></span>
<span data-ttu-id="2a9e5-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="2a9e5-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="2a9e5-114">當您用 Skype Server 2015 部署執行壓力及效能工具，您，在最低限度下，必須符合您的測試中每個 4500 使用者這些硬體需求：</span><span class="sxs-lookup"><span data-stu-id="2a9e5-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="2a9e5-115">1gb 網路介面卡</span><span class="sxs-lookup"><span data-stu-id="2a9e5-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="2a9e5-116">8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="2a9e5-116">8 GB RAM</span></span>
    
- <span data-ttu-id="2a9e5-117">2 顆雙核心 Cpu</span><span class="sxs-lookup"><span data-stu-id="2a9e5-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="2a9e5-118">用戶端軟體需求</span><span class="sxs-lookup"><span data-stu-id="2a9e5-118">Client software requirements</span></span>
<span data-ttu-id="2a9e5-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="2a9e5-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="2a9e5-120">支援的作業系統壓力及效能工具包括：</span><span class="sxs-lookup"><span data-stu-id="2a9e5-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="2a9e5-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="2a9e5-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="2a9e5-122">Windows Server 2008 （64 位元）</span><span class="sxs-lookup"><span data-stu-id="2a9e5-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="2a9e5-123">此外，電腦必須符合下列軟體需求：</span><span class="sxs-lookup"><span data-stu-id="2a9e5-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="2a9e5-124">您必須安裝 Microsoft.NET 4.5 架構。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="2a9e5-125">下載.Net 4.5 以下架構。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="2a9e5-126">您必須在 Windows 中啟用桌面體驗功能。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="2a9e5-127">您將需要 Microsoft Visual c + + 2013 (x64) 安裝。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="2a9e5-128">在這裡下載 Visual c + + 2013</span><span class="sxs-lookup"><span data-stu-id="2a9e5-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="2a9e5-129">您要需要用 Skype Server 2015 成功部署。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="2a9e5-130">組態需求</span><span class="sxs-lookup"><span data-stu-id="2a9e5-130">Configuration requirements</span></span>
<span data-ttu-id="2a9e5-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="2a9e5-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="2a9e5-132">您將需要這些額外的組態，為了順利執行壓力及效能工具：</span><span class="sxs-lookup"><span data-stu-id="2a9e5-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="2a9e5-133">您要的網域或本機系統管理員群組成員身分登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="2a9e5-134">您無法安裝 Skype for Business Server 2015 使用者建立工具 (UserProvisioningTool.exe) 上的使用者帳戶所在的任何前端伺服器或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="2a9e5-135">當使用者建立工具會執行多次時，每個已啟用 Microsoft 整合通訊的使用者必須有唯一的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="2a9e5-136">分頁檔案大小應系統管理或否則您必須是至少 1.5 倍 RAM 的數量電腦系統中。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="2a9e5-137">安裝 Skype for Business Server 2015 壓力及效能工具</span><span class="sxs-lookup"><span data-stu-id="2a9e5-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="2a9e5-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="2a9e5-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="2a9e5-139">安裝無法比較簡單。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="2a9e5-140">您必須執行 Windows Installer 檔案， **CapacityPlanningTool.msi**，每個您要用於模擬使用者流量，並在每個前端伺服器集區您將在其中建立使用者與連絡人的用戶端電腦上。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="2a9e5-141">若要下載.msi，以及我們其他文章所述的範例指令碼中，移至下載中心連結：[商務用 Skype Server 2015、 壓力及效能工具](https://www.microsoft.com/download/details.aspx?id=50367)。</span><span class="sxs-lookup"><span data-stu-id="2a9e5-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

