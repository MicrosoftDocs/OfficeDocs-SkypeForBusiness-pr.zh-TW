---
title: Microsoft Teams 的安全性指南
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: 在工作場所中從共用電腦安全地使用 Microsoft Teams 的指導方針。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45497c824cfc20644a59e35f7812b17058f61c2c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117051"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a><span data-ttu-id="cf9bb-103">在共用電腦上安全地使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf9bb-103">Use Microsoft Teams securely on shared computers</span></span>

<span data-ttu-id="cf9bb-104">如果可能，*建議* 企業對用戶端裝置使用「零信任」方法，運用裝置管理功能、裝置健康情況檢查和原則強制執行、裝置層級加密及其他安全性功能。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-104">When possible, it is *recommended* Enterprises make use of a Zero Trust approach to client devices making use of device management capabilities, device health checks and policy enforcement, device-level encryption, and other security features.</span></span>

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="零信任的圖片，在藍色圓形中顯示明確驗證、最低權限以及承擔入侵 (零信任原則的核心)。":::

<span data-ttu-id="cf9bb-106">系統管理員可以透過 *堅持* 驗證、最低權限，以及承擔入侵 (即會對使用者和資料造成最低風險動作的標準)，藉此建立非常安全的條件。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-106">Administrators can create very secure conditions by *insisting* on verification, least privilege, and by assuming compromise -- standards that lead to actions that minimize risk to both users and data.</span></span>

> [!TIP]
> <span data-ttu-id="cf9bb-107">若要更深入檢查零信任原則，請參閱[這些影片](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537)。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-107">For a deeper examination of Zero Trust principles, see [these videos](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span></span>

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a><span data-ttu-id="cf9bb-108">從共用電腦安全地使用 Microsoft Teams 安全的秘訣</span><span class="sxs-lookup"><span data-stu-id="cf9bb-108">Tips for using Microsoft Teams securely from a shared computer</span></span>

<span data-ttu-id="cf9bb-109">我們意識到此做法可能並非在所有情況下都可行，但安全性系統管理員仍務必遵循從共用電腦或非管理裝置使用 Teams 的指導方針。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-109">Recognizing that this may not be possible or practical in all scenarios, it is still important for security administrators to follow guidance for using Teams from a shared computer or unmanaged device as best they can.</span></span>

<span data-ttu-id="cf9bb-110">應該開發方案，以盡快、盡可能遵守指導方針。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-110">Plans should be developed to adhere to guidelines as promptly as is possible.</span></span>

1. <span data-ttu-id="cf9bb-111">使用作業系統平台安全性功能。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-111">Make use of Operating System platform security capabilities.</span></span>
    1. <span data-ttu-id="cf9bb-112">確保作業系統已設定為透過作業系統提供者安裝自動更新 (若為 Microsoft 系統，可透過 [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq) 來完成此動作)。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-112">Ensure that the operating system is configured to install automatic updates from the Operating System provider (for Microsoft systems, this can be accomplished via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span></span> 
    1. <span data-ttu-id="cf9bb-113">確保已啟用任何裝置加密功能 (例如 [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview))，以及用來存取裝置的金鑰受到保護。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-113">Ensure that any device encryption capabilities such as [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview) are enabled, and the key used to access the device is secured.</span></span>  <span data-ttu-id="cf9bb-114">請注意，大多數的 [**Windows 10 裝置支援 BitLocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-114">Note that most modern [**Windows 10 devices support bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).</span></span> 
    1. <span data-ttu-id="cf9bb-115">在您的裝置上使用防毒功能，例如 [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 提供的功能。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-115">Use anti-virus capabilities such as those offered by [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) on your devices.</span></span>
    1. <span data-ttu-id="cf9bb-116">強烈建議對系統的每個使用者使用[個別使用者帳戶](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account)。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-116">Use of [separate user accounts](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) for each user of the system is highly recommended.</span></span>
    1. <span data-ttu-id="cf9bb-117">*請勿* 對非系統管理功能 (例如瀏覽網頁、執行 Teams 等) 授與或使用系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-117">*Do not* grant, or use, administrator privileges for non-administrative functions (such as browsing the web, running Teams, et cetera).</span></span>

<span data-ttu-id="cf9bb-118">如果不符合上述指導方針，我們建議使用額外的瀏覽器安全性最佳做法：</span><span class="sxs-lookup"><span data-stu-id="cf9bb-118">If the above guidance cannot be met, we recommend making use of additional browser security best practices:</span></span>

1. <span data-ttu-id="cf9bb-119">運用瀏覽器的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-119">Leverage browser security capabilities.</span></span>
    1. <span data-ttu-id="cf9bb-120">使用私人瀏覽工作階段，將保存到磁碟的資料和歷程記錄最小化。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-120">Use private browsing sessions to minimize data and history that persists to disk.</span></span> <span data-ttu-id="cf9bb-121">例如，[在 Microsoft Edge 中使用 inPrivate 瀏覽](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate)、[在 Google Chrome中進行無痕式瀏覽](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en)，或使用您的特定瀏覽器用於私人瀏覽的功能。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-121">For example, use [inPrivate browsing in Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Incognito browsing in Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), or the capabilities your specific browser for browsing privately.</span></span> 
    1. <span data-ttu-id="cf9bb-122">建議將系統行為變更為 *預設* 採用私人瀏覽。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-122">Changing the system behavior to engage private browsing *by default* is recommended.</span></span> 

2. <span data-ttu-id="cf9bb-123">瀏覽至並使用 [Teams Web 應用程式](https://teams.microsoft.com) (有時稱為 *Web* 用戶端)，而非可下載的Teams 用戶端。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-123">Browse to and use the [Teams web app](https://teams.microsoft.com) (sometimes called the *web* client) not the downloadable Teams client.</span></span>

3. <span data-ttu-id="cf9bb-124">使用共用系統完成之後，您必須：</span><span class="sxs-lookup"><span data-stu-id="cf9bb-124">When you are done using the shared system, you must:</span></span> 
    1. <span data-ttu-id="cf9bb-125">[登出 Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487)。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-125">[Sign out of Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span></span>
    1. <span data-ttu-id="cf9bb-126">關閉所有瀏覽器索引標籤和視窗。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-126">Close all browser tabs and windows.</span></span>
    1. <span data-ttu-id="cf9bb-127">從裝置登出。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-127">Sign out of the device.</span></span>

<span data-ttu-id="cf9bb-128">上述項目並非涵蓋所有情況的最佳做法或安全性控制項的完整清單，且可能會在您的環境中採取額外的動作 (例如，如果您有 [Office 365 ATP 方案 1 或 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)，安全性系統管理員可以選擇對 Teams 使用安全連結和安全附件)。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-128">The items above are not a comprehensive list of best practices or security controls covering all cases, and there may be extra actions that can be taken in your environment, (for instance, security administrators may choose to use Safe Links and Safe Attachments for Teams if you have [Office 365 ATP Plan 1 or 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span></span> <span data-ttu-id="cf9bb-129">不過，這些步驟可做為建立從共用裝置使用 Teams 指導方針的起點。</span><span class="sxs-lookup"><span data-stu-id="cf9bb-129">However, these steps are a starting point for building guidance for using Teams from shared devices.</span></span>

## <a name="more-information"></a><span data-ttu-id="cf9bb-130">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="cf9bb-130">More Information</span></span>

[<span data-ttu-id="cf9bb-131">Configuration Manager 中的 Bitlocker</span><span class="sxs-lookup"><span data-stu-id="cf9bb-131">Bitlocker in Configuration Manager</span></span>](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[<span data-ttu-id="cf9bb-132">Intune 中 Windows 10 的 BitLocker 原則</span><span class="sxs-lookup"><span data-stu-id="cf9bb-132">Bitlocker for Windows 10 in Intune</span></span>](/mem/intune/protect/encrypt-devices)

[<span data-ttu-id="cf9bb-133">Intune 中的端點安全性</span><span class="sxs-lookup"><span data-stu-id="cf9bb-133">Endpoint security in Intune</span></span>](/mem/intune/protect/endpoint-security)

<span data-ttu-id="cf9bb-134">在您的 Windows 安全性中[啟用](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender 防毒軟體，並[執行掃描](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span><span class="sxs-lookup"><span data-stu-id="cf9bb-134">[Enable](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus in your Windows Security and [run scans](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span></span>

[<span data-ttu-id="cf9bb-135">Microsoft Defender 安全性中心文章</span><span class="sxs-lookup"><span data-stu-id="cf9bb-135">Microsoft Defender security center article</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[<span data-ttu-id="cf9bb-136">Teams Web 用戶端/Teams Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="cf9bb-136">Teams web client/teams web app</span></span>](./get-clients.md#web-client)

[<span data-ttu-id="cf9bb-137">安全性和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf9bb-137">Security and Microsoft Teams</span></span>](./teams-security-guide.md)