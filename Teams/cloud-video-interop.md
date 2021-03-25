---
title: Microsoft Teams 雲端視訊 Interop。
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: 使用雲端視像交互操作做為中間解決方案，讓協力廠商會議室裝置加入 Microsoft Teams 會議。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a8d657e2cbc12695453e26ef0e4bf9ad55070bf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122357"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="42e7c-103">Microsoft Teams 雲端視訊 Interop。</span><span class="sxs-lookup"><span data-stu-id="42e7c-103">Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="42e7c-104">雲端視 (CVI) 是 Microsoft 合格協力廠商解決方案，可讓協力廠商會議室 (網真) 和個人視像裝置 (RVC) 加入 Microsoft Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="42e7c-104">Cloud Video Interop (CVI) is a Microsoft Qualified third-party solution that enables third-party meeting rooms (telepresence) and personal video devices (VTCs) to join Microsoft Teams meetings.</span></span>
 
<span data-ttu-id="42e7c-105">有了 Microsoft Teams，您可以在會議取得豐富的線上內容共同功能，包括音訊、視像和內容共用。</span><span class="sxs-lookup"><span data-stu-id="42e7c-105">With Microsoft Teams, you get rich online content collaboration in meetings that include audio, video, and content sharing.</span></span> <span data-ttu-id="42e7c-106">您可以透過桌面和 Web 用戶端，以及許多原生與 Microsoft Teams 整合的合作夥伴裝置來享受這項功能。</span><span class="sxs-lookup"><span data-stu-id="42e7c-106">This can be enjoyed through the desktop and web client, as well as through many partner devices that integrate natively with Microsoft Teams.</span></span> <span data-ttu-id="42e7c-107">不過，許多客戶已經投資在視距電話會議和個人視像通訊裝置上，升級可能會非常貴。</span><span class="sxs-lookup"><span data-stu-id="42e7c-107">However, many customers have already invested in video teleconferencing and personal video communication devices, which can be expensive to upgrade.</span></span> <span data-ttu-id="42e7c-108">雲端視像交互操作提供簡單的解決方案，讓您持續使用現有的解決方案，直到您準備好升級。</span><span class="sxs-lookup"><span data-stu-id="42e7c-108">Cloud Video Interop provides an easy solution, allowing you to keep using your existing solutions until you are ready to upgrade.</span></span>

<span data-ttu-id="42e7c-109">Microsoft Teams 使用雲端視像交互操作功能，為所有參與者提供原生會議體驗 ，包括會議室或 Teams 用戶端內部。</span><span class="sxs-lookup"><span data-stu-id="42e7c-109">With Cloud Video Interop, Microsoft Teams delivers a native meeting experience for all participants – in meeting rooms or inside of Teams clients.</span></span>

### <a name="is-cloud-video-interop-for-me"></a><span data-ttu-id="42e7c-110">我是否適合使用雲端視像交互操作？</span><span class="sxs-lookup"><span data-stu-id="42e7c-110">Is Cloud Video Interop for me?</span></span>

<span data-ttu-id="42e7c-111">當您使用 Teams 端點轉換至完整原生 Microsoft Teams 解決方案時，雲端視像交互操作會提供一個中間服務。</span><span class="sxs-lookup"><span data-stu-id="42e7c-111">Cloud Video Interop provides an intermediate service while you transition to a full native Microsoft Teams Solution, using Teams endpoints.</span></span> <span data-ttu-id="42e7c-112">提供的服務應該是移移路徑的一部分。</span><span class="sxs-lookup"><span data-stu-id="42e7c-112">The service provided should be part of your migration path.</span></span>

<span data-ttu-id="42e7c-113">雲端視訊交互操作適用于符合下列準則的客戶：</span><span class="sxs-lookup"><span data-stu-id="42e7c-113">Cloud Video Interop is intended for customers who meet the following criteria:</span></span>

- <span data-ttu-id="42e7c-114">在超過 50 個 (裝置上部署會議室裝置和個人視) ，但無法與 Microsoft Teams 直接整合</span><span class="sxs-lookup"><span data-stu-id="42e7c-114">Have a large deployment of meeting room devices and personal video devices deployment (50+ devices) that are not qualified for direct integration with Microsoft Teams</span></span>
- <span data-ttu-id="42e7c-115">我們的其中一個雲端視像交互操作合作夥伴支援</span><span class="sxs-lookup"><span data-stu-id="42e7c-115">Are supported by one of our Cloud Video Interop partners</span></span>
- <span data-ttu-id="42e7c-116">想要在移向原生 Microsoft Teams 解決方案期間，保留目前會議室裝置和個人視像裝置的投資價值</span><span class="sxs-lookup"><span data-stu-id="42e7c-116">Want to retain the value of their investment in their current meeting room devices and personal video devices during the migration to a native Microsoft Teams solution</span></span>

<span data-ttu-id="42e7c-117">雖然雲端視像交互操作提供很好的中間解決方案，但我們鼓勵客戶長期研究原生的 Teams 會議解決方案 ，例如 Teams 會議室系統。</span><span class="sxs-lookup"><span data-stu-id="42e7c-117">While Cloud Video Interop provides a great intermediate solution, we encourage our customers to look into our native Teams Meeting solutions, such as Teams Room Systems, for the long term.</span></span> 

### <a name="office-365-us-government-and-third-party-services"></a><span data-ttu-id="42e7c-118">Office 365 美國政府版和協力廠商服務</span><span class="sxs-lookup"><span data-stu-id="42e7c-118">Office 365 US Government and third-party services</span></span>

<span data-ttu-id="42e7c-119">Office 365 提供將協力廠商應用程式整合至 SharePoint Online 網站、商務用 Skype、Teams、企業用 Microsoft 365 應用程式中包含的 Office 應用程式 (例如 Word、Excel、PowerPoint 和 Outlook) 和 Outlook Web App 的能力。</span><span class="sxs-lookup"><span data-stu-id="42e7c-119">Office 365 provides the ability to integrate third-party applications into SharePoint Online sites, Skype for Business, Teams, Office applications included in Microsoft 365 Apps for enterprise (such as Word, Excel, PowerPoint, and Outlook), and Outlook Web App.</span></span> <span data-ttu-id="42e7c-120">此外，Office 365 支援協力廠商服務提供者的整合。</span><span class="sxs-lookup"><span data-stu-id="42e7c-120">In addition, Office 365 supports integration with third-party service providers.</span></span> <span data-ttu-id="42e7c-121">這些協力廠商應用程式和服務可能涉及在 Office 365 基礎結構外的協力廠商系統上儲存、傳送及處理貴組織的客戶資料，因此不在 Office 365 合規性和資料保護承諾的涵蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="42e7c-121">These third-party applications and services might involve storing, transmitting, and processing your organization's customer data on third-party systems that are outside of the Office 365 infrastructure and therefore are not covered by the Office 365 compliance and data protection commitments.</span></span> <span data-ttu-id="42e7c-122">**建議您在評估貴組織適當使用這些服務時，審查協力廠商所提供的隱私權與合規性聲明。**</span><span class="sxs-lookup"><span data-stu-id="42e7c-122">**It is recommended that you review the privacy and compliance statements provided by the third parties when assessing the appropriate use of these services for your organization.**</span></span>



### <a name="partners-certified-for-microsoft-teams"></a><span data-ttu-id="42e7c-123">Microsoft Teams 合作夥伴認證</span><span class="sxs-lookup"><span data-stu-id="42e7c-123">Partners Certified for Microsoft Teams</span></span>

<span data-ttu-id="42e7c-124">下列合作夥伴提供適用于 Microsoft Teams 的影片交互操作解決方案。</span><span class="sxs-lookup"><span data-stu-id="42e7c-124">The following partners have video interop solutions for Microsoft Teams.</span></span> <span data-ttu-id="42e7c-125">您的公司可能會選擇在企業內與這些合作夥伴的任何組合合作。</span><span class="sxs-lookup"><span data-stu-id="42e7c-125">Your company may choose to work with any combination of these partners within your enterprise.</span></span> 

|<span data-ttu-id="42e7c-126">夥伴</span><span class="sxs-lookup"><span data-stu-id="42e7c-126">Partner</span></span>|<span data-ttu-id="42e7c-127">合作夥伴解決方案</span><span class="sxs-lookup"><span data-stu-id="42e7c-127">Partner solution</span></span>|
|----|---|
|![代表 Poly RealConnect 的標誌](media/polycom.png) | <span data-ttu-id="42e7c-129"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a></span><span class="sxs-lookup"><span data-stu-id="42e7c-129"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a></span></span> |
|![代表 Pexip 無限的標誌](media/pexip.png)| <span data-ttu-id="42e7c-131"><a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft Teams 的 Pexip 無限</a></span><span class="sxs-lookup"><span data-stu-id="42e7c-131"><a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity for Microsoft Teams</a></span></span> | 
|![代表 BlueJeans 閘道的標誌](media/bluejeans.png)| <span data-ttu-id="42e7c-133"><a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft Teams 的 BlueJeans 閘道</a></span><span class="sxs-lookup"><span data-stu-id="42e7c-133"><a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway for Microsoft Teams</a></span></span> |
|![代表 Cisco CVI 的標誌](media/cisco.png)|<span data-ttu-id="42e7c-135"><a href="https://aka.ms/CiscoCVI" target="_blank">Microsoft Teams 的 Cisco Webex 影片整合</a></span><span class="sxs-lookup"><span data-stu-id="42e7c-135"><a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration for Microsoft Teams</a></span></span>|

### <a name="cloud-video-interop-overview"></a><span data-ttu-id="42e7c-136">雲端視像交互操作概觀</span><span class="sxs-lookup"><span data-stu-id="42e7c-136">Cloud Video Interop overview</span></span>

<span data-ttu-id="42e7c-137">Cloud Video Interop 是一項協力廠商服務，由我們的合作夥伴提供，提供現有視訊會議與內部部署個人視像裝置解決方案與 Microsoft Teams 之間的互通性。</span><span class="sxs-lookup"><span data-stu-id="42e7c-137">Cloud Video Interop is a third-party service that is offered by our partners to provide interoperability between existing video conferencing and personal video device solutions on premises, and Microsoft Teams.</span></span>

<span data-ttu-id="42e7c-138">我們的合作夥伴提供的解決方案包含可部署完全雲端或部分/完全內部部署的元件。</span><span class="sxs-lookup"><span data-stu-id="42e7c-138">The solutions offered by our partners consist of components that can be deployed either fully cloud based or partially/fully on premises.</span></span> 
     
<span data-ttu-id="42e7c-139">下圖顯示合作夥伴解決方案的高層級架構。</span><span class="sxs-lookup"><span data-stu-id="42e7c-139">The following diagram shows the high-level architecture of our partner solutions.</span></span>

![描述 Teams Cloud Video Interop 合作夥伴解決方案的圖表](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a><span data-ttu-id="42e7c-141">部署雲端視像交互操作</span><span class="sxs-lookup"><span data-stu-id="42e7c-141">Deploy Cloud Video Interop</span></span>

<span data-ttu-id="42e7c-142">部署雲端視像交互操作解決方案時，您必須瞭解您部署的合作夥伴解決方案。</span><span class="sxs-lookup"><span data-stu-id="42e7c-142">When deploying a Cloud Video Interop solution, it's important to understand that you are deploying a partner solution.</span></span> <span data-ttu-id="42e7c-143">以下圖表列出部署雲端視像交互操作時應該採取一般步驟。</span><span class="sxs-lookup"><span data-stu-id="42e7c-143">The general steps you should take to deploy Cloud Video Interop are listed in the following diagram.</span></span>

![描述在貴組織中部署 CVI 的圖表](media/deploying-cvi.png)

### <a name="plan"></a><span data-ttu-id="42e7c-145">規劃</span><span class="sxs-lookup"><span data-stu-id="42e7c-145">Plan</span></span>

<span data-ttu-id="42e7c-146">在計畫階段期間，您應該找出不會以原生 Teams 裝置取代的裝置，並尋找可支援這些裝置的雲端視像交互操作合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="42e7c-146">During the plan phase, you should identify the devices that you will not replace with a native Teams device, and find a Cloud Video Interop partner that can support these devices.</span></span>  

<span data-ttu-id="42e7c-147">另外，您必須瞭解，每位將排程會議的使用者都需要授權，才能讓啟用雲端視像交互操作功能的裝置加入會議。</span><span class="sxs-lookup"><span data-stu-id="42e7c-147">It's also important to understand that you will need a license for each user who will schedule meetings in which you want a Cloud Video Interop-enabled device to join.</span></span> <span data-ttu-id="42e7c-148">請注意，確切的授權需求可以從雲端視像交互操作合作夥伴取得。</span><span class="sxs-lookup"><span data-stu-id="42e7c-148">Note that exact licensing requirements can be obtained from the Cloud Video Interop partner.</span></span> <span data-ttu-id="42e7c-149">在您開始部署之前，請確保清除這項功能。</span><span class="sxs-lookup"><span data-stu-id="42e7c-149">Ensure that this is clear before you start your deployment.</span></span>

### <a name="configure"></a><span data-ttu-id="42e7c-150">配置</span><span class="sxs-lookup"><span data-stu-id="42e7c-150">Configure</span></span>

<span data-ttu-id="42e7c-151">您選擇進行 CVI 部署的合作夥伴會提供完整的部署檔，該檔包含在貴組織中成功部署所需的所有步驟。</span><span class="sxs-lookup"><span data-stu-id="42e7c-151">The partner that you have chosen for your CVI deployment will provide you with a full deployment document that consists of all the steps needed to deploy successfully within your organization.</span></span> <span data-ttu-id="42e7c-152">這包括防火牆埠和 IP 範圍、裝置設定變更，以及其他需要變更的設定。</span><span class="sxs-lookup"><span data-stu-id="42e7c-152">This will include firewall ports and IP ranges, configuration changes for your devices, and other settings that need to change.</span></span>

### <a name="provision"></a><span data-ttu-id="42e7c-153">提供</span><span class="sxs-lookup"><span data-stu-id="42e7c-153">Provision</span></span>  

<span data-ttu-id="42e7c-154">在部署階段期間，您將根據合作夥伴組組指南指派授權給適當的使用者。</span><span class="sxs-lookup"><span data-stu-id="42e7c-154">During the provision phase, you will assign licenses to the appropriate users according to the partner configuration guide.</span></span> <span data-ttu-id="42e7c-155">您也需要執行 Azure 同意程式，才能讓合作夥伴存取您的 Teams 環境。</span><span class="sxs-lookup"><span data-stu-id="42e7c-155">You will also need to go through the Azure Consent process to provide the partner access to your Teams environment.</span></span> <span data-ttu-id="42e7c-156">請參閱 [Microsoft 身分識別平臺端點](/azure/active-directory/develop/v2-permissions-and-consent) 的許可權與同意，以取得 Azure 同意程式詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="42e7c-156">See [Permissions and consent in the Microsoft identity platform endpoint](/azure/active-directory/develop/v2-permissions-and-consent) for more information about the Azure consent process.</span></span>

### <a name="schedule"></a><span data-ttu-id="42e7c-157">附表</span><span class="sxs-lookup"><span data-stu-id="42e7c-157">Schedule</span></span>

<span data-ttu-id="42e7c-158">使用者啟用雲端視像交互操作後，任何使用 Teams 會議 Outlook 會議附加元件或 Teams 用戶端排程的會議，都會自動將適當的額外資訊新加入 Teams 會議，讓雲端視像交互操作相容的裝置可以加入這些會議。</span><span class="sxs-lookup"><span data-stu-id="42e7c-158">After a user is enabled for Cloud Video Interop, any meeting scheduled using either the Teams Meeting Add-in for Outlook or the Teams Client will have the appropriate additional information automatically added into the Teams meeting so that Cloud Video Interop-compatible devices can join these meetings.</span></span>

### <a name="join"></a><span data-ttu-id="42e7c-159">加入</span><span class="sxs-lookup"><span data-stu-id="42e7c-159">Join</span></span>

<span data-ttu-id="42e7c-160">根據合作夥伴解決方案，有幾種方法可以加入啟用雲端視像交互操作的會議。</span><span class="sxs-lookup"><span data-stu-id="42e7c-160">Depending on the partner solution, there are several ways to join a Cloud Video Interop-enabled meeting.</span></span> <span data-ttu-id="42e7c-161">您的雲端視像交互操作合作夥伴會提供確切的會議加入案例。</span><span class="sxs-lookup"><span data-stu-id="42e7c-161">Exact meeting join scenarios will be provided by your Cloud Video Interop partner.</span></span> <span data-ttu-id="42e7c-162">我們在下面列出一些範例：</span><span class="sxs-lookup"><span data-stu-id="42e7c-162">We've listed some examples below:</span></span>

- <span data-ttu-id="42e7c-163">IVR (互動式語音回應) </span><span class="sxs-lookup"><span data-stu-id="42e7c-163">IVR (Interactive Voice Response)</span></span> 
  - <span data-ttu-id="42e7c-164">您可以使用電話號碼撥入合作夥伴的 IVR tenantkey@domain。</span><span class="sxs-lookup"><span data-stu-id="42e7c-164">You can dial in to the partner's IVR using the tenantkey@domain.</span></span>
  - <span data-ttu-id="42e7c-165">當您在合作夥伴 IVR 中時，系統會提示您輸入 VTC meetingId，然後將您連接到 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="42e7c-165">When you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="42e7c-166">直撥</span><span class="sxs-lookup"><span data-stu-id="42e7c-166">Direct dial</span></span> 
  - <span data-ttu-id="42e7c-167">您可以使用直接撥號功能，使用完整的租使用者金鑰字串，直接撥入 Teams 會議，而不與合作夥伴的 IVR 互動。VTC ConferenceId@domain。</span><span class="sxs-lookup"><span data-stu-id="42e7c-167">You can directly dial in to the Teams meeting without interacting with the partner's IVR by using the direct dial feature, using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="42e7c-168">單鍵撥號</span><span class="sxs-lookup"><span data-stu-id="42e7c-168">One-touch dial</span></span> 
  - <span data-ttu-id="42e7c-169">如果您有整合的 Teams 會議室，您可以使用合作夥伴提供的單鍵撥號功能 (不需要輸入任何撥號字串) 。</span><span class="sxs-lookup"><span data-stu-id="42e7c-169">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

## <a name="manage-cloud-video-interop"></a><span data-ttu-id="42e7c-170">管理雲端視像交交互操作</span><span class="sxs-lookup"><span data-stu-id="42e7c-170">Manage Cloud Video Interop</span></span>

<span data-ttu-id="42e7c-171">部署雲端視像交互操作之後，您可以使用合作夥伴提供的解決方案來管理裝置。</span><span class="sxs-lookup"><span data-stu-id="42e7c-171">After Cloud Video Interop is deployed, you can manage the devices using the solutions provided by our partners.</span></span> <span data-ttu-id="42e7c-172">每個合作夥伴都會提供一個包含授權和裝置管理的管理介面。</span><span class="sxs-lookup"><span data-stu-id="42e7c-172">Each partner will provide you with an administrative interface that will include both license and device management.</span></span> 

<span data-ttu-id="42e7c-173">報告也可以直接從合作夥伴系統管理介面使用。</span><span class="sxs-lookup"><span data-stu-id="42e7c-173">Reporting is also available directly from the partner administrative interface.</span></span> <span data-ttu-id="42e7c-174">如需報告功能詳細資訊，請聯絡您所選擇的合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="42e7c-174">For more information on reporting capabilities, contact the partner of your choice.</span></span> 

### <a name="troubleshooting-cloud-video-interop"></a><span data-ttu-id="42e7c-175">雲端視像交互操作疑難排解</span><span class="sxs-lookup"><span data-stu-id="42e7c-175">Troubleshooting Cloud Video Interop</span></span>

<span data-ttu-id="42e7c-176">雲端視像交互操作是合作夥伴提供的服務。</span><span class="sxs-lookup"><span data-stu-id="42e7c-176">Cloud Video Interop is a partner-provided service.</span></span> <span data-ttu-id="42e7c-177">如果您遇到問題，第一個步驟是連接已安裝 Teams 用戶端的裝置，並連接到與造成問題的雲端視像交互操作裝置相同的區段。</span><span class="sxs-lookup"><span data-stu-id="42e7c-177">If you are experiencing issues, the first step is to connect a device that has the Teams Client installed and connect it to the same segment as the Cloud Video Interop device that is causing problems.</span></span> 

<span data-ttu-id="42e7c-178">如果 Teams 在此區段中能正確工作，而且您也遵循合作夥伴提供的所有網路和組組指導方針，您必須與合作夥伴聯繫，以進一步疑難排解。</span><span class="sxs-lookup"><span data-stu-id="42e7c-178">If Teams functions correctly on this segment, and you have also followed all the networking and configuration guidelines the partner has provided, you will need to contact the partner for further troubleshooting.</span></span> 

## <a name="powershell-for-cloud-video-interop"></a><span data-ttu-id="42e7c-179">PowerShell for Cloud Video Interop</span><span class="sxs-lookup"><span data-stu-id="42e7c-179">PowerShell for Cloud Video Interop</span></span>

<span data-ttu-id="42e7c-180">您可以使用下列 PowerShell Cmdlet 來 (部分) 雲端視像交互操作部署。</span><span class="sxs-lookup"><span data-stu-id="42e7c-180">The following PowerShell cmdlets are available for you to (partially) automate the Cloud Video Interop deployment.</span></span>

- <span data-ttu-id="42e7c-181">**Get-CsTeamsVideoInteropServicepolicy：Microsoft** 會針對每個支援的合作夥伴提供預先建構的策略，讓您指定要用於雲端視訊交互 () 的合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="42e7c-181">**Get-CsTeamsVideoInteropServicepolicy**: Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for Cloud Video Interop.</span></span><br><span data-ttu-id="42e7c-182">此 Cmdlet 可讓您識別可在貴組織中使用的預先建構策略。</span><span class="sxs-lookup"><span data-stu-id="42e7c-182">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="42e7c-183">您可以使用 Cmdlet，將這個Grant-CsTeamsVideoInteropServicePolicy指派給一Grant-CsTeamsVideoInteropServicePolicy使用者。</span><span class="sxs-lookup"><span data-stu-id="42e7c-183">You can assign this policy to one or more of your users by leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
- <span data-ttu-id="42e7c-184">**Grant-CsTeamsVideoInteropServicePolicy：** 此 Cmdlet 可讓您指派預先建構的策略，供貴組織使用，或將策略指派給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="42e7c-184">**Grant-CsTeamsVideoInteropServicePolicy**: This cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
- <span data-ttu-id="42e7c-185">**New-CsVideoInteropServiceProvider：** 使用此 Cmdlet 來指定貴組織想使用之支援的 CVI 合作夥伴相關資訊。</span><span class="sxs-lookup"><span data-stu-id="42e7c-185">**New-CsVideoInteropServiceProvider**: Use this cmdlet to specify information about a supported CVI partner that your organization would like to use.</span></span>
- <span data-ttu-id="42e7c-186">**Set-CsVideoInteropServiceProvider：** 使用此 Cmdlet 更新貴組織使用之支援的 CVI 合作夥伴相關資訊。</span><span class="sxs-lookup"><span data-stu-id="42e7c-186">**Set-CsVideoInteropServiceProvider**: Use this cmdlet to update information about a supported CVI partner that your organization uses.</span></span>
- <span data-ttu-id="42e7c-187">**Get-CsVideoInteropServiceProvider：** 使用此 Cmdlet 取得組織中所有已配置的提供者。</span><span class="sxs-lookup"><span data-stu-id="42e7c-187">**Get-CsVideoInteropServiceProvider**: Use this cmdlet to get all of the providers that have been configured for use within the organization.</span></span>
- <span data-ttu-id="42e7c-188">**Remove-CsVideoInteropServiceProvider：** 使用此 Cmdlet 移除貴組織不再使用之提供者的所有提供者資訊。</span><span class="sxs-lookup"><span data-stu-id="42e7c-188">**Remove-CsVideoInteropServiceProvider**: Use this cmdlet to remove all provider information about a provider that your organization no longer uses.</span></span>