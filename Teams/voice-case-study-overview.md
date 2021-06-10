---
title: Teams Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams多國公司的語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097489"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="3d07e-103">Contoso 案例研究：Teams語音移移概觀</span><span class="sxs-lookup"><span data-stu-id="3d07e-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="3d07e-104">本文介紹一個案例分析，瞭解一家虛構的多國公司 Contoso 如何為組織Teams語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="3d07e-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="3d07e-105">Contoso 已部署 Microsoft 365 企業版，並針對下列專案解決主要設計決策和實現詳細資料：網路、身分識別、Windows 10 企業版、Office 365 專業增強版、行動裝置管理、資訊保護、安全性、從 商務用 Skype 升級至 Teams、電話系統 和音訊會議。</span><span class="sxs-lookup"><span data-stu-id="3d07e-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="3d07e-106">本文著重說明 Contoso 如何將內部部署使用者移Teams統一通訊、共同合作和語音。</span><span class="sxs-lookup"><span data-stu-id="3d07e-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="3d07e-107">有關 Contoso 如何使用 Microsoft 雲端服務加速其數位轉換的背景資訊，請參閱從 [Contoso](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)案例研究概觀開始的所有核心文章。</span><span class="sxs-lookup"><span data-stu-id="3d07e-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="3d07e-108">在核心文章中，您可以找到下列相關資訊：</span><span class="sxs-lookup"><span data-stu-id="3d07e-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="3d07e-109">Contoso 的 IT 基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="3d07e-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="3d07e-110">網路</span><span class="sxs-lookup"><span data-stu-id="3d07e-110">Networking</span></span>
- <span data-ttu-id="3d07e-111">Identity</span><span class="sxs-lookup"><span data-stu-id="3d07e-111">Identity</span></span>
- <span data-ttu-id="3d07e-112">Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="3d07e-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="3d07e-113">Office 365 Pro加號</span><span class="sxs-lookup"><span data-stu-id="3d07e-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="3d07e-114">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="3d07e-114">Mobile device management</span></span>
- <span data-ttu-id="3d07e-115">資訊保護</span><span class="sxs-lookup"><span data-stu-id="3d07e-115">Information protection</span></span>
- <span data-ttu-id="3d07e-116">安全性Microsoft 365 企業版摘要</span><span class="sxs-lookup"><span data-stu-id="3d07e-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="3d07e-117">最高機密專案的小組</span><span class="sxs-lookup"><span data-stu-id="3d07e-117">Team for a top-secret project</span></span>
- <span data-ttu-id="3d07e-118">SharePoint高度機密數位資產的線上網站</span><span class="sxs-lookup"><span data-stu-id="3d07e-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="3d07e-119">若要取得規劃升級的資訊，您首先想要從快速入門[開始Microsoft Teams升級](upgrade-start-here.md)。</span><span class="sxs-lookup"><span data-stu-id="3d07e-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="3d07e-120">Contoso 商務目標Teams</span><span class="sxs-lookup"><span data-stu-id="3d07e-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="3d07e-121">若要將內部部署使用者遷移到Teams通訊、共同合作和語音，Contoso 決定下列商業目標：</span><span class="sxs-lookup"><span data-stu-id="3d07e-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="3d07e-122">Teams啟用</span><span class="sxs-lookup"><span data-stu-id="3d07e-122">Teams enablement</span></span> 

  <span data-ttu-id="3d07e-123">Contoso 的一致通訊和共同Teams提供正確的政策，以管理及啟用安全的內部和外部共同合作。</span><span class="sxs-lookup"><span data-stu-id="3d07e-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="3d07e-124">從商務用 Skype 升級至 Teams</span><span class="sxs-lookup"><span data-stu-id="3d07e-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="3d07e-125">商務用 Skype在 Contoso 中廣泛部署。</span><span class="sxs-lookup"><span data-stu-id="3d07e-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="3d07e-126">由於需要移轉舊版系統，Contoso 決定將其使用者商務用 Skype升級Teams。</span><span class="sxs-lookup"><span data-stu-id="3d07e-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="3d07e-127">詳細資訊，請參閱[Contoso 案例研究：Teams方案](voice-case-study-migration-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="3d07e-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="3d07e-128">電話系統</span><span class="sxs-lookup"><span data-stu-id="3d07e-128">Phone System</span></span>  

  <span data-ttu-id="3d07e-129">商務用 Skype企業語音功能廣泛部署在 Contoso 中。</span><span class="sxs-lookup"><span data-stu-id="3d07e-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="3d07e-130">由於需要將舊版系統移轉為中繼伺服器的下一個躍點，Contoso 將其商務用 Skype企業語音使用者移電話系統。</span><span class="sxs-lookup"><span data-stu-id="3d07e-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="3d07e-131">Contoso 網站使用 Microsoft 通話方案、電話系統直接路由，或兩者的組合。</span><span class="sxs-lookup"><span data-stu-id="3d07e-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="3d07e-132">詳細資訊，請參閱[Contoso 案例研究：電話系統。](voice-case-study-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="3d07e-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="3d07e-133">依位置路由</span><span class="sxs-lookup"><span data-stu-id="3d07e-133">Location-Based Routing</span></span> 

  <span data-ttu-id="3d07e-134">在受電話規範的國家/地區擁有辦公室位置，Contoso 需要重新Location-Based部署中目前商務用 Skype路由電話系統路由。</span><span class="sxs-lookup"><span data-stu-id="3d07e-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="3d07e-135">詳細資訊，請參閱 [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="3d07e-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="3d07e-136">緊急電話</span><span class="sxs-lookup"><span data-stu-id="3d07e-136">Emergency Calling</span></span> 

  <span data-ttu-id="3d07e-137">在已執行直接路由的地方，Contoso 會與核准的協力廠商設定緊急電話。</span><span class="sxs-lookup"><span data-stu-id="3d07e-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="3d07e-138">詳細資訊，請參閱 [Contoso 案例研究：緊急電話](voice-case-study-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="3d07e-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="3d07e-139">音訊會議</span><span class="sxs-lookup"><span data-stu-id="3d07e-139">Audio Conferencing</span></span> 

  <span data-ttu-id="3d07e-140">Contoso 會設定其 SIP 主幹上託管至 PSTN 提供者的音訊會議服務號碼。</span><span class="sxs-lookup"><span data-stu-id="3d07e-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="3d07e-141">詳細資訊，請參閱 [Contoso 案例研究：音訊會議](voice-case-study-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="3d07e-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="3d07e-142">Local Media 優化</span><span class="sxs-lookup"><span data-stu-id="3d07e-142">Local Media Optimization</span></span> 

  <span data-ttu-id="3d07e-143">Contoso 在有一個直接路由主幹至遠端網站所Microsoft 電話系統的位置，運用了 Local Media 優化。</span><span class="sxs-lookup"><span data-stu-id="3d07e-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="3d07e-144">詳細資訊，請參閱[規劃本地媒體優化和](direct-routing-media-optimization.md)[設定本地媒體優化](direct-routing-media-optimization-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="3d07e-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="3d07e-145">自動電話機和通話佇列</span><span class="sxs-lookup"><span data-stu-id="3d07e-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="3d07e-146">由於 Covid-19，Contoso 想要在員工遠端工作期間提供接待員支援。</span><span class="sxs-lookup"><span data-stu-id="3d07e-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="3d07e-147">Contoso 使用自動電話機和通話佇列來管理接收者電話號碼的來電。</span><span class="sxs-lookup"><span data-stu-id="3d07e-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="3d07e-148">詳細資訊，請參閱 [Contoso 案例研究：自動總機和通話佇列](voice-case-study-call-queues.md)。</span><span class="sxs-lookup"><span data-stu-id="3d07e-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>