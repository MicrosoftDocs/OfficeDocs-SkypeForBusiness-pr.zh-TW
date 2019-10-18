---
title: 資料收集做法
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: true
description: Microsoft 會收集人口普查、使用方式及錯誤資料，以瞭解商務用 Skype 的使用方式，以及使用者遇到問題的位置。 資料可用來規劃產品的改良功能。
ms.openlocfilehash: d5e4e72ac06eb0638ed25dbf48321afd22b503ed
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571843"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="4425c-104">商務用 Skype 和 Microsoft 團隊資料收集做法</span><span class="sxs-lookup"><span data-stu-id="4425c-104">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="4425c-105">商務用 skype Server 及商務用 skype Online，以及商務用 Skype 和 Microsoft 團隊 app，收集資料以協助 Microsoft 瞭解這些產品的使用方式，以及發生的錯誤類型（例如登入錯誤）。</span><span class="sxs-lookup"><span data-stu-id="4425c-105">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="4425c-106">此資訊可協助我們瞭解使用模式、規劃新功能，以及疑難排解及修正問題區域。</span><span class="sxs-lookup"><span data-stu-id="4425c-106">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="4425c-107">當您自動收集一些使用資料時，只有當系統管理員和/或使用者選擇允許時，才能收集其他資料。</span><span class="sxs-lookup"><span data-stu-id="4425c-107">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="4425c-108">資料收集分為下列三種類別：</span><span class="sxs-lookup"><span data-stu-id="4425c-108">Data collection falls into these three categories:</span></span>

- <span data-ttu-id="4425c-109">人口普查資料</span><span class="sxs-lookup"><span data-stu-id="4425c-109">Census data</span></span>

- <span data-ttu-id="4425c-110">使用量資料</span><span class="sxs-lookup"><span data-stu-id="4425c-110">Usage data</span></span>

- <span data-ttu-id="4425c-111">錯誤報表資料</span><span class="sxs-lookup"><span data-stu-id="4425c-111">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="4425c-112">人口普查資料</span><span class="sxs-lookup"><span data-stu-id="4425c-112">Census data</span></span>

<span data-ttu-id="4425c-113">人口普查資料是專為提供、支援及改善商務用 Skype 而取得的。</span><span class="sxs-lookup"><span data-stu-id="4425c-113">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="4425c-114">Microsoft 團隊及商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="4425c-114">Microsoft Teams, and Skype for Business Online.</span></span> <span data-ttu-id="4425c-115">它包含諸如裝置與作業系統版本等環境資訊，以及地區和語言設定。</span><span class="sxs-lookup"><span data-stu-id="4425c-115">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="4425c-116">它也包含登入嘗試與失敗的計數器。</span><span class="sxs-lookup"><span data-stu-id="4425c-116">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="4425c-117">以下是收集的統計資料的一些特定範例：</span><span class="sxs-lookup"><span data-stu-id="4425c-117">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="4425c-118">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4425c-118">**Data type**</span></span>|<span data-ttu-id="4425c-119">**範例**</span><span class="sxs-lookup"><span data-stu-id="4425c-119">**Example**</span></span>|<span data-ttu-id="4425c-120">**筆記**</span><span class="sxs-lookup"><span data-stu-id="4425c-120">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4425c-121">AppName</span><span class="sxs-lookup"><span data-stu-id="4425c-121">AppName</span></span>  <br/> |<span data-ttu-id="4425c-122">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="4425c-122">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="4425c-123">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="4425c-123">DeviceModel</span></span>  <br/> |<span data-ttu-id="4425c-124">iPhone</span><span class="sxs-lookup"><span data-stu-id="4425c-124">iPhone</span></span>  <br/> ||
|<span data-ttu-id="4425c-125">OSName</span><span class="sxs-lookup"><span data-stu-id="4425c-125">OSName</span></span>  <br/> |<span data-ttu-id="4425c-126">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="4425c-126">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="4425c-127">OSVersion</span><span class="sxs-lookup"><span data-stu-id="4425c-127">OSVersion</span></span>  <br/> |<span data-ttu-id="4425c-128">8.3</span><span class="sxs-lookup"><span data-stu-id="4425c-128">8.3</span></span>  <br/> ||
|<span data-ttu-id="4425c-129">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="4425c-129">UserLanguage</span></span>  <br/> |<span data-ttu-id="4425c-130">EN-US</span><span class="sxs-lookup"><span data-stu-id="4425c-130">EN-US</span></span>  <br/> ||
|<span data-ttu-id="4425c-131">UserID</span><span class="sxs-lookup"><span data-stu-id="4425c-131">UserID</span></span>  <br/> |<span data-ttu-id="4425c-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="4425c-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="4425c-133">此識別碼的雜湊是兩次：一次在用戶端，然後再次在遙測服務。</span><span class="sxs-lookup"><span data-stu-id="4425c-133">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="4425c-134">雜湊確保 ID 無法連結至特定使用者。</span><span class="sxs-lookup"><span data-stu-id="4425c-134">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="4425c-135">DeviceID</span><span class="sxs-lookup"><span data-stu-id="4425c-135">DeviceID</span></span>  <br/> |<span data-ttu-id="4425c-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="4425c-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="4425c-137">裝置識別碼是一個 GUID，在裝置上隨機產生一次並傳送到遙測服務。</span><span class="sxs-lookup"><span data-stu-id="4425c-137">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="4425c-138">人口普查資料不包含任何可識別貴組織或使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="4425c-138">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="4425c-139">如需詳細資訊，請參閱[商務用 Skype 隱私權聲明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4425c-139">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="4425c-140">人口統計資料預設為開啟，且無法由系統管理員或使用者關閉。</span><span class="sxs-lookup"><span data-stu-id="4425c-140">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="4425c-141">使用量資料</span><span class="sxs-lookup"><span data-stu-id="4425c-141">Usage data</span></span>

<span data-ttu-id="4425c-142">使用方式資料包括諸如撥打數、送出或接收的 Im 數、已加入的會議數量、所使用的功能及穩定性問題等資訊。</span><span class="sxs-lookup"><span data-stu-id="4425c-142">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="4425c-143">使用狀況資料可能包含識別貴組織的資訊，例如 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="4425c-143">Usage data might contain information that identifies your organization, such as contoso.com.</span></span> <span data-ttu-id="4425c-144">以下是收集的用法資料的一些特定範例：</span><span class="sxs-lookup"><span data-stu-id="4425c-144">Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="4425c-145">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4425c-145">**Data type**</span></span>|<span data-ttu-id="4425c-146">**範例**</span><span class="sxs-lookup"><span data-stu-id="4425c-146">**Example**</span></span>|<span data-ttu-id="4425c-147">**筆記**</span><span class="sxs-lookup"><span data-stu-id="4425c-147">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4425c-148">傳送的 IM</span><span class="sxs-lookup"><span data-stu-id="4425c-148">IM Sent</span></span>  <br/> |<span data-ttu-id="4425c-149">之間</span><span class="sxs-lookup"><span data-stu-id="4425c-149">12</span></span>  <br/> ||
|<span data-ttu-id="4425c-150">已接收 IM</span><span class="sxs-lookup"><span data-stu-id="4425c-150">IM Received</span></span>  <br/> |<span data-ttu-id="4425c-151">500</span><span class="sxs-lookup"><span data-stu-id="4425c-151">5</span></span>  <br/> ||
|<span data-ttu-id="4425c-152">加入會議（嘗試）</span><span class="sxs-lookup"><span data-stu-id="4425c-152">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="4425c-153">500</span><span class="sxs-lookup"><span data-stu-id="4425c-153">5</span></span>  <br/> ||
|<span data-ttu-id="4425c-154">加入會議（成功）</span><span class="sxs-lookup"><span data-stu-id="4425c-154">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="4425c-155">4</span><span class="sxs-lookup"><span data-stu-id="4425c-155">4</span></span>  <br/> ||
|<span data-ttu-id="4425c-156">通話/會議紀要</span><span class="sxs-lookup"><span data-stu-id="4425c-156">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="4425c-157">30分鐘</span><span class="sxs-lookup"><span data-stu-id="4425c-157">30 mins</span></span>  <br/> ||
|<span data-ttu-id="4425c-158">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="4425c-158">FederationPartner</span></span>  <br/> |<span data-ttu-id="4425c-159">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4425c-159">Microsoft.com</span></span>  <br/> |<span data-ttu-id="4425c-160">這是在 Office 365 中註冊並以明文傳送的組織名稱，這表示它不會被混淆。</span><span class="sxs-lookup"><span data-stu-id="4425c-160">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="4425c-161">使用量資料不包含任何可識別使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="4425c-161">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="4425c-162">使用方式資料收集預設為開啟，但內部部署系統管理員可以使用商務用 Skype Server 上的 [DisableAutomaticSendTracing] 群組原則設定將它關閉。</span><span class="sxs-lookup"><span data-stu-id="4425c-162">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="4425c-163">關閉此設定會影響組織中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="4425c-163">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="4425c-164">如需詳細資訊，請參閱[設定用戶端引導原則](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)。</span><span class="sxs-lookup"><span data-stu-id="4425c-164">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="4425c-165">最終使用者無法開啟或關閉使用資料收集。</span><span class="sxs-lookup"><span data-stu-id="4425c-165">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="4425c-166">針對 Skype 會議應用程式和加入啟動器網頁，控制遙測的方式是透過此原則進行：</span><span class="sxs-lookup"><span data-stu-id="4425c-166">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="4425c-167">此原則預設為 false，因此預設會關閉遙測收集。</span><span class="sxs-lookup"><span data-stu-id="4425c-167">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="4425c-168">此設定為 [每個池]，並控制所有與 Skype 會議應用程式連線的使用者，以及在該伺服器上主持的會議。</span><span class="sxs-lookup"><span data-stu-id="4425c-168">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="4425c-169">錯誤報表資料</span><span class="sxs-lookup"><span data-stu-id="4425c-169">Error reporting data</span></span>

<span data-ttu-id="4425c-170">錯誤報表資料可包含有關效能、可靠性、裝置設定、網路連線品質、錯誤代碼、錯誤記錄和例外狀況的資訊。</span><span class="sxs-lookup"><span data-stu-id="4425c-170">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="4425c-171">以下是收集的錯誤報表資料的一些特定範例：</span><span class="sxs-lookup"><span data-stu-id="4425c-171">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="4425c-172">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4425c-172">**Data type**</span></span>|<span data-ttu-id="4425c-173">**範例**</span><span class="sxs-lookup"><span data-stu-id="4425c-173">**Example**</span></span>|<span data-ttu-id="4425c-174">**筆記**</span><span class="sxs-lookup"><span data-stu-id="4425c-174">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4425c-175">訊息方向</span><span class="sxs-lookup"><span data-stu-id="4425c-175">Message direction</span></span>  <br/> |<span data-ttu-id="4425c-176">入帳</span><span class="sxs-lookup"><span data-stu-id="4425c-176">Incoming</span></span>  <br/> ||
|<span data-ttu-id="4425c-177">交談狀態</span><span class="sxs-lookup"><span data-stu-id="4425c-177">Conversation state</span></span>  <br/> |<span data-ttu-id="4425c-178">超過</span><span class="sxs-lookup"><span data-stu-id="4425c-178">Idle</span></span>  <br/> ||
|<span data-ttu-id="4425c-179">交談執行緒識別碼</span><span class="sxs-lookup"><span data-stu-id="4425c-179">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="4425c-180">AdDO8hsJqilU93hQHC3OZaPR2saEA = =</span><span class="sxs-lookup"><span data-stu-id="4425c-180">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="4425c-181">UserID</span><span class="sxs-lookup"><span data-stu-id="4425c-181">UserID</span></span>  <br/> |<span data-ttu-id="4425c-182">amosmarble</span><span class="sxs-lookup"><span data-stu-id="4425c-182">amosmarble</span></span> <br/> |<span data-ttu-id="4425c-183">識別碼是以明文傳送，在儲存前，遙測服務的雜湊值</span><span class="sxs-lookup"><span data-stu-id="4425c-183">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="4425c-184">錯誤報表資料也可能包含個人身分識別的資訊，例如使用者的 IP 位址及會話初始通訊協定統一資源識別項（SIP URI）。</span><span class="sxs-lookup"><span data-stu-id="4425c-184">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="4425c-185">如需收集項目的詳細說明，請參閱[商務用 Skype 隱私權聲明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4425c-185">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="4425c-186">錯誤報表需要兩個專案：</span><span class="sxs-lookup"><span data-stu-id="4425c-186">Error reporting requires two things:</span></span>

- <span data-ttu-id="4425c-187">在伺服器或租使用者系統管理中心的 [DisableAutomaticSendTracing] 群組原則設定為 False 時（這是預設狀態）。</span><span class="sxs-lookup"><span data-stu-id="4425c-187">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="4425c-188">如需詳細資訊，請參閱[設定用戶端引導原則](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)。</span><span class="sxs-lookup"><span data-stu-id="4425c-188">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="4425c-189">使用者可從 [一般] 索引標籤個別加入宣告，在![商務用 Skype 用戶端中](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) ，按一下齒輪圖示代表齒輪的圖示，然後在顯示 [**一般**] 索引標籤的 [**選項**] 對話方塊中開啟。</span><span class="sxs-lookup"><span data-stu-id="4425c-189">End users individually opt in from the General tab (click the gear icon ![An icon that represents a gear ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![[選項] 對話方塊中 [資料收集] 核取方塊的螢幕擷取畫面](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="4425c-191">若是 Skype 會議應用程式，MeetingUxEnableTelemetry 也會控制錯誤報表，但在 Windows 上，Watson 設定會控制上傳損毀資訊。</span><span class="sxs-lookup"><span data-stu-id="4425c-191">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="4425c-192">您可以在 [桌面用戶端] 對話方塊中看到 Skype 會議應用程式的使用者設定。</span><span class="sxs-lookup"><span data-stu-id="4425c-192">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="4425c-193">如需詳細資訊，請參閱[設定商務用 Skype 中的一般選項](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)。</span><span class="sxs-lookup"><span data-stu-id="4425c-193">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="4425c-194">您可以參閱為[商務用 Skype Online 設定您的網路](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)，以設定您的網路。</span><span class="sxs-lookup"><span data-stu-id="4425c-194">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="4425c-195">如果您使用的是中國由世紀運營的 Office 365，請參閱[針對由世紀運營的商務用 Skype Online 設定您的網路](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)。</span><span class="sxs-lookup"><span data-stu-id="4425c-195">If you are using Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4425c-196">相關主題</span><span class="sxs-lookup"><span data-stu-id="4425c-196">Related topics</span></span>
[<span data-ttu-id="4425c-197">客戶經驗改進計畫</span><span class="sxs-lookup"><span data-stu-id="4425c-197">Customer Experience Improvement Program</span></span>](https://www.microsoft.com/products/ceip/default.mspx)

[<span data-ttu-id="4425c-198">適用于音訊會議與通話方案的國家和地區可用性</span><span class="sxs-lookup"><span data-stu-id="4425c-198">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
