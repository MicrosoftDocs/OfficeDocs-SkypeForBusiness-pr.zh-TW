---
title: 團隊語音 Contoso 案例研究
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
description: 多國企業的小組語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701221"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="4ae0e-103">Contoso 案例研究：團隊語音遷移概覽</span><span class="sxs-lookup"><span data-stu-id="4ae0e-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="4ae0e-104">本文將針對虛構的多國企業（Contoso）如何針對其組織實施小組語音方案，提供案例研究。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="4ae0e-105">Contoso 已部署 Microsoft 365 企業版並解決主要的設計決策及實現詳細資料：網路、身分識別、Windows 10 企業版、Office 365 專業增強版、行動裝置管理、資訊保護、安全性、從商務用 Skype 升級至團隊、手機系統和音訊會議。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="4ae0e-106">本文重點說明 Contoso 如何將內部部署使用者遷移至小組，以進行整合溝通、共同作業及語音。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="4ae0e-107">如需 Contoso 如何使用 Microsoft 的雲端服務加速其數位轉換的背景資訊，請參閱從 [Contoso 案例研究概覽](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)開始的所有核心文章。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="4ae0e-108">在核心文章中，您會發現下列資訊：</span><span class="sxs-lookup"><span data-stu-id="4ae0e-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="4ae0e-109">Contoso 的 IT 基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="4ae0e-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="4ae0e-110">網</span><span class="sxs-lookup"><span data-stu-id="4ae0e-110">Networking</span></span>
- <span data-ttu-id="4ae0e-111">Identity</span><span class="sxs-lookup"><span data-stu-id="4ae0e-111">Identity</span></span>
- <span data-ttu-id="4ae0e-112">Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="4ae0e-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="4ae0e-113">Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="4ae0e-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="4ae0e-114">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="4ae0e-114">Mobile device management</span></span>
- <span data-ttu-id="4ae0e-115">資訊保護</span><span class="sxs-lookup"><span data-stu-id="4ae0e-115">Information protection</span></span>
- <span data-ttu-id="4ae0e-116">Microsoft 365 企業安全性摘要</span><span class="sxs-lookup"><span data-stu-id="4ae0e-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="4ae0e-117">小組中的主要專案</span><span class="sxs-lookup"><span data-stu-id="4ae0e-117">Team for a top-secret project</span></span>
- <span data-ttu-id="4ae0e-118">高機密數位資產的 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="4ae0e-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="4ae0e-119">如需規劃升級的相關資訊，您必須先開始進行 [Microsoft 團隊升級](upgrade-start-here.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="4ae0e-120">Contoso 企業團隊的商務目標</span><span class="sxs-lookup"><span data-stu-id="4ae0e-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="4ae0e-121">若要將內部部署使用者遷移至小組，以進行整合溝通、共同作業及語音作業，Contoso 決定下列業務目標：</span><span class="sxs-lookup"><span data-stu-id="4ae0e-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="4ae0e-122">團隊啟用</span><span class="sxs-lookup"><span data-stu-id="4ae0e-122">Teams enablement</span></span> 

  <span data-ttu-id="4ae0e-123">Contoso 的整合通訊與共同作業小組已啟用正確的原則來管理及啟用安全的內部與外部共同作業。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="4ae0e-124">從商務用 Skype 升級至 Teams</span><span class="sxs-lookup"><span data-stu-id="4ae0e-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="4ae0e-125">商務用 Skype 是在 Contoso 中廣泛部署。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="4ae0e-126">如果您需要移出舊版系統，Contoso 決定將商務用 Skype 使用者升級至團隊。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="4ae0e-127">如需詳細資訊，請參閱 [Contoso 案例研究：團隊升級方案](voice-case-study-migration-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="4ae0e-128">電話系統</span><span class="sxs-lookup"><span data-stu-id="4ae0e-128">Phone System</span></span>  

  <span data-ttu-id="4ae0e-129">使用企業語音的商務用 Skype 已在 Contoso 中廣泛部署。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="4ae0e-130">如果您需要移離其中繼伺服器下一個躍點的舊版系統，Contoso 已將商務用 Skype 企業語音使用者遷移至 [電話系統]。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="4ae0e-131">Contoso 網站使用 Microsoft 通話方案、電話系統直傳送或兩者的組合。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="4ae0e-132">如需詳細資訊，請參閱 [Contoso 案例研究： [電話系統](voice-case-study-phone-system.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="4ae0e-133">依位置路由</span><span class="sxs-lookup"><span data-stu-id="4ae0e-133">Location-Based Routing</span></span> 

  <span data-ttu-id="4ae0e-134">在電話管控國家/地區的 office 位置，Contoso 需要在手機系統部署中，重新建立在商務用 Skype 中所提供的 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="4ae0e-135">如需詳細資訊，請參閱 [Contoso 案例研究： Location-Based 路由](voice-case-study-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="4ae0e-136">緊急電話</span><span class="sxs-lookup"><span data-stu-id="4ae0e-136">Emergency Calling</span></span> 

  <span data-ttu-id="4ae0e-137">在直接佈線已實施的位置，Contoso 利用核准的協力廠商設定緊急通話。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="4ae0e-138">如需詳細資訊，請參閱 [Contoso 案例研究：緊急通話](voice-case-study-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="4ae0e-139">音訊會議</span><span class="sxs-lookup"><span data-stu-id="4ae0e-139">Audio Conferencing</span></span> 

  <span data-ttu-id="4ae0e-140">Contoso 將其 SIP 主幹上託管的音訊會議服務號碼設定為 PSTN 提供者。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="4ae0e-141">如需詳細資訊，請參閱 [Contoso 案例研究：音訊會議](voice-case-study-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="4ae0e-142">本機媒體優化</span><span class="sxs-lookup"><span data-stu-id="4ae0e-142">Local Media Optimization</span></span> 

  <span data-ttu-id="4ae0e-143">Contoso 利用本機媒體優化功能，可讓他們將一個直接路由主幹移至遠端網站所利用的 Microsoft Phone 系統。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="4ae0e-144">如需詳細資訊，請參閱 [規劃本機媒體優化](direct-routing-media-optimization.md) 並 [設定本機媒體優化](direct-routing-media-optimization-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="4ae0e-145">自動語音應答及呼叫佇列</span><span class="sxs-lookup"><span data-stu-id="4ae0e-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="4ae0e-146">Covid-19 之後，Contoso 想要在員工進行遠端作業時提供接待員支援。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="4ae0e-147">Contoso 使用自動語音應答及呼叫佇列，管理來電的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="4ae0e-148">如需詳細資訊，請參閱 [Contoso 案例研究：自動語音應答及呼叫佇列](voice-case-study-call-queues.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae0e-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


