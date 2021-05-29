---
title: 運算子連線
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 深入瞭解運算子連線，例如需求與部署規劃。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088b36f546cebe67e10d840075e601e96a6df6e2
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694538"
---
# <a name="plan-for-operator-connect"></a><span data-ttu-id="590ce-103">規劃運算子連線</span><span class="sxs-lookup"><span data-stu-id="590ce-103">Plan for Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="590ce-104">運算子連線目前僅適用于公用 **預覽**。</span><span class="sxs-lookup"><span data-stu-id="590ce-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="590ce-105">公開預覽可讓您測試即將推出的功能，並提供意見回饋。</span><span class="sxs-lookup"><span data-stu-id="590ce-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="590ce-106">公用預覽中包含的功能可能不完整、可能會變更，且雲端版Office 365 政府版支援。</span><span class="sxs-lookup"><span data-stu-id="590ce-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Cloud.</span></span>

<span data-ttu-id="590ce-107">運算子連線是提供公用交換電話網絡與 PSTN (PSTN) 與Teams電話系統。</span><span class="sxs-lookup"><span data-stu-id="590ce-107">Operator Connect is another option for providing Public Switched Telephone Network (PSTN) connectivity with Teams and Phone System.</span></span>  

<span data-ttu-id="590ce-108">本文將說明權益和需求，並列出參與運算子和連線運算子。</span><span class="sxs-lookup"><span data-stu-id="590ce-108">This article describes benefits and requirements, and lists the operators participating in the Operator Connect Program.</span></span>  <span data-ttu-id="590ce-109">如果您決定運算子連線是貴組織正確的解決方案，請參閱閱讀本文後[，請參閱設定](operator-connect-configure.md)運算子連線。</span><span class="sxs-lookup"><span data-stu-id="590ce-109">If you decide Operator Connect is the right solution for your organization, after reading this article, see [Configure Operator Connect](operator-connect-configure.md).</span></span>  

## <a name="benefits"></a><span data-ttu-id="590ce-110">優點</span><span class="sxs-lookup"><span data-stu-id="590ce-110">Benefits</span></span>

<span data-ttu-id="590ce-111">使用運算子連線，如果您現有的接線員是 Microsoft Operator 連線 計畫的參與者，他們可以管理將 PSTN 通話Teams。</span><span class="sxs-lookup"><span data-stu-id="590ce-111">With Operator Connect, if your existing operator is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="590ce-112">運算子連線計畫提供下列優點：</span><span class="sxs-lookup"><span data-stu-id="590ce-112">The Operator Connect program provides the following benefits:</span></span>

- <span data-ttu-id="590ce-113">**利用現有合約，或尋找新的運算子。**</span><span class="sxs-lookup"><span data-stu-id="590ce-113">**Leverage existing contracts, or find a new operator.**</span></span> <span data-ttu-id="590ce-114">您可以保留您偏好的運算子和合約，或從一系列參與的營運者中選擇新的，以滿足您的業務需求。</span><span class="sxs-lookup"><span data-stu-id="590ce-114">You keep your preferred operator and contracts, or choose a new one from a selection of participating operators to meet your business needs.</span></span>

- <span data-ttu-id="590ce-115">**運算子管理的基礎結構。**</span><span class="sxs-lookup"><span data-stu-id="590ce-115">**Operator-managed infrastructure.**</span></span> <span data-ttu-id="590ce-116">您的接線員會管理 PSTN 通話服務和會話邊界控制器 (SBC) ，讓您節省硬體購買和管理。</span><span class="sxs-lookup"><span data-stu-id="590ce-116">Your operator manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

- <span data-ttu-id="590ce-117">**更快速、更輕鬆地部署。**</span><span class="sxs-lookup"><span data-stu-id="590ce-117">**Faster, easier deployment.**</span></span> <span data-ttu-id="590ce-118">您可以快速連接到您的接線員，並將電話號碼指派給使用者 ---全部Teams系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="590ce-118">You can quickly connect to your operator and assign phone numbers to users -– all from the Teams Admin Center.</span></span>

- <span data-ttu-id="590ce-119">**增強的支援和可靠性。**</span><span class="sxs-lookup"><span data-stu-id="590ce-119">**Enhanced support and reliability.**</span></span> <span data-ttu-id="590ce-120">業者提供技術支援和共用服務等級協定以改善支援服務，而由 Azure 提供直接對等功能則建立一對一網路連接，以提高可靠性。</span><span class="sxs-lookup"><span data-stu-id="590ce-120">Operators provide technical support and shared service level agreements to improve support service, while direct peering powered by Azure creates a one-to-one network connection for enhanced reliability.</span></span>

## <a name="requirements"></a><span data-ttu-id="590ce-121">需求</span><span class="sxs-lookup"><span data-stu-id="590ce-121">Requirements</span></span>

 <span data-ttu-id="590ce-122">如果連線運算子或運算子，可能是適用于貴組織的解決方案：</span><span class="sxs-lookup"><span data-stu-id="590ce-122">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="590ce-123">您的地理位置無法提供 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="590ce-123">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="590ce-124">您偏好的運算子是 Microsoft Operator 連線參與者。</span><span class="sxs-lookup"><span data-stu-id="590ce-124">Your preferred operator is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="590ce-125">您想要尋找新的運算子，以在 Teams。</span><span class="sxs-lookup"><span data-stu-id="590ce-125">You want to find a new operator to enable calling in Teams.</span></span>

<span data-ttu-id="590ce-126">若要使用運算子連線電話號碼指派，請確定您的使用者為：</span><span class="sxs-lookup"><span data-stu-id="590ce-126">To enable phone number assignments with Operator Connect, make sure your users are:</span></span>

- <span data-ttu-id="590ce-127">Teams 電話授權。</span><span class="sxs-lookup"><span data-stu-id="590ce-127">Teams Phone licensed.</span></span> <span data-ttu-id="590ce-128">若要深入瞭解，請參閱[什麼是電話系統？，Teams](what-is-phone-system-in-office-365.md)[指派附加元件授權給使用者](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="590ce-128">To learn more, see [What is Phone System?](what-is-phone-system-in-office-365.md) and [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>
- <span data-ttu-id="590ce-129">在 TeamsOnly 模式中。</span><span class="sxs-lookup"><span data-stu-id="590ce-129">In TeamsOnly mode.</span></span> <span data-ttu-id="590ce-130">若要深入瞭解，[請參閱瞭解Microsoft Teams商務用 Skype及互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="590ce-130">To learn more, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

## <a name="available-operators"></a><span data-ttu-id="590ce-131">可用的運算子</span><span class="sxs-lookup"><span data-stu-id="590ce-131">Available Operators</span></span>

<span data-ttu-id="590ce-132">下列運算子是 Microsoft Operator 連線參與者：</span><span class="sxs-lookup"><span data-stu-id="590ce-132">The following operators are participants in the Microsoft Operator Connect program:</span></span>

| <span data-ttu-id="590ce-133">運算元</span><span class="sxs-lookup"><span data-stu-id="590ce-133">Operator</span></span> | <span data-ttu-id="590ce-134">功能</span><span class="sxs-lookup"><span data-stu-id="590ce-134">Capability</span></span> | <span data-ttu-id="590ce-135">國家/地區涵蓋範圍</span><span class="sxs-lookup"><span data-stu-id="590ce-135">Country coverage</span></span> |
| --- | --- | --- |
| `BT`  | <span data-ttu-id="590ce-136">通話</span><span class="sxs-lookup"><span data-stu-id="590ce-136">Calling</span></span> | <span data-ttu-id="590ce-137">比利時、丹麥、芬蘭、法國、德國、愛爾蘭、義大利、盧森堡、荷蘭、挪威、波蘭、南非、西班牙、瑞典、瑞士、英國</span><span class="sxs-lookup"><span data-stu-id="590ce-137">Belgium, Denmark, Finland, France, Germany, Ireland, Italy, Luxembourg, Netherlands, Norway, Poland, South Africa, Spain, Sweden, Switzerland, United Kingdom</span></span> |
| `Intrado` | <span data-ttu-id="590ce-138">通話</span><span class="sxs-lookup"><span data-stu-id="590ce-138">Calling</span></span> | <span data-ttu-id="590ce-139">比利時、加拿大、丹麥、法國、德國、愛爾蘭、盧森堡、荷蘭、西班牙、瑞典、英國、美國</span><span class="sxs-lookup"><span data-stu-id="590ce-139">Belgium, Canada, Denmark, France, Germany, Ireland, Luxembourg, Netherlands, Spain, Sweden, United Kingdom, United States</span></span>  |
| `NTT`  | <span data-ttu-id="590ce-140">通話</span><span class="sxs-lookup"><span data-stu-id="590ce-140">Calling</span></span> | <span data-ttu-id="590ce-141">奧地利、比利時、巴西、加拿大、捷克、丹麥、芬蘭、法國、德國、愛爾蘭、義大利、盧森堡、墨西哥、荷蘭、挪威、波蘭、葡萄牙、波多黎各、羅馬尼亞、南非、西班牙、瑞典、瑞士、英國、美國</span><span class="sxs-lookup"><span data-stu-id="590ce-141">Austria, Belgium, Brazil, Canada, Czechia, Denmark, Finland,  France, Germany, Ireland, Italy, Luxembourg, Mexico, Netherlands, Norway, Poland, Portugal, Puerto Rico, Romania, South Africa, Spain, Sweden, Switzerland, United Kingdom, United States</span></span> |
| `NuWave` | <span data-ttu-id="590ce-142">通話</span><span class="sxs-lookup"><span data-stu-id="590ce-142">Calling</span></span> | <span data-ttu-id="590ce-143">奧地利、比利時、加拿大、丹麥、法國、德國、愛爾蘭、義大利、荷蘭、葡萄牙、西班牙、瑞典、瑞士、英國、美國</span><span class="sxs-lookup"><span data-stu-id="590ce-143">Austria, Belgium, Canada, Denmark, France, Germany, Ireland, Italy, Netherlands, Portugal, Spain, Sweden, Switzerland, United Kingdom, United States</span></span>   |
| `Orange Business Services` | <span data-ttu-id="590ce-144">通話</span><span class="sxs-lookup"><span data-stu-id="590ce-144">Calling</span></span> | <span data-ttu-id="590ce-145">奧地利、比利時、捷克、丹麥、芬蘭、法國、法屬圭亞那、德國、哥德洛普、愛爾蘭、義大利、盧森堡、馬提克、馬約特、荷蘭、挪威、波蘭、葡萄牙、留尼翁、聖巴塞萊米、聖馬德、西班牙、斯瓦爾巴德、瑞典、瑞士、英國</span><span class="sxs-lookup"><span data-stu-id="590ce-145">Austria, Belgium, Czechia, Denmark, Finland, France, French Guiana, Germany, Guadeloupe, Ireland, Italy, Luxembourg, Martinique, Mayotte, Netherlands, Norway, Poland, Portugal, Réunion, Saint Barthélemy, Saint Martin, Spain, Svalbard, Sweden, Switzerland, United Kingdom</span></span>  |
| `Pure IP` | <span data-ttu-id="590ce-146">通話</span><span class="sxs-lookup"><span data-stu-id="590ce-146">Calling</span></span> | <span data-ttu-id="590ce-147">澳大利亞、奧地利、比利時、巴西、保加利亞、加拿大、智利、哥倫比亞、克羅地亞、賽普勒斯、捷克、丹麥、芬蘭、法國、德國、希臘、香港特別行政區、愛爾蘭、義大利、日本、立陶宛、盧森堡、馬來西亞、墨西哥、荷蘭、紐西蘭、挪威、巴薩、波蘭、葡萄牙、波多黎各、羅馬尼亞、新加坡、斯洛伐克、斯洛維尼亞、南非、西班牙、瑞典、瑞士、英國、美國</span><span class="sxs-lookup"><span data-stu-id="590ce-147">Australia, Austria, Belgium, Brazil, Bulgaria, Canada, Chile, Colombia, Croatia, Cyprus, Czechia, Denmark, Finland, France, Germany, Greece, Hong Kong S.A.R., Ireland, Italy, Japan, Lithuania, Luxembourg, Malaysia, Mexico, Netherlands, New Zealand, Norway, Panama, Poland, Portugal, Puerto Rico, Romania, Singapore, Slovakia, Slovenia, South Africa, Spain, Sweden, Switzerland, United Kingdom, United States</span></span>  |
| `Rogers Business` | <span data-ttu-id="590ce-148">通話</span><span class="sxs-lookup"><span data-stu-id="590ce-148">Calling</span></span> | <span data-ttu-id="590ce-149">加拿大</span><span class="sxs-lookup"><span data-stu-id="590ce-149">Canada</span></span>  |
| `TATA Communications` | <span data-ttu-id="590ce-150">通話</span><span class="sxs-lookup"><span data-stu-id="590ce-150">Calling</span></span> | <span data-ttu-id="590ce-151">澳大利亞、奧地利、比利時、加拿大、捷克、丹麥、法國、德國、香港特別行政區、匈牙利、愛爾蘭、義大利、馬來西亞、墨西哥、荷蘭、紐西蘭、波蘭、葡萄牙、羅馬尼亞、新加坡、韓國、西班牙、瑞典、瑞士、泰國、英國、美國</span><span class="sxs-lookup"><span data-stu-id="590ce-151">Australia, Austria, Belgium, Canada, Czechia, Denmark, France, Germany, Hong Kong S.A.R., Hungary, Ireland, Italy, Malaysia, Mexico, Netherlands, New Zealand, Poland, Portugal, Romania, Singapore, South Korea, Spain, Sweden, Switzerland, Thailand, United Kingdom, United States</span></span> |
| `Telekom Deutschland` | <span data-ttu-id="590ce-152">通話</span><span class="sxs-lookup"><span data-stu-id="590ce-152">Calling</span></span> | <span data-ttu-id="590ce-153">德國</span><span class="sxs-lookup"><span data-stu-id="590ce-153">Germany</span></span>  |
| `Telenor` | <span data-ttu-id="590ce-154">通話</span><span class="sxs-lookup"><span data-stu-id="590ce-154">Calling</span></span> | <span data-ttu-id="590ce-155">丹麥、芬蘭、挪威、瑞典</span><span class="sxs-lookup"><span data-stu-id="590ce-155">Denmark, Finland, Norway, Sweden</span></span>  |
| `Verizon` | <span data-ttu-id="590ce-156">通話</span><span class="sxs-lookup"><span data-stu-id="590ce-156">Calling</span></span> | <span data-ttu-id="590ce-157">美國</span><span class="sxs-lookup"><span data-stu-id="590ce-157">United States</span></span> |