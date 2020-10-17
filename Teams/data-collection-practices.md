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
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: 瞭解 Microsoft 如何收集人口普查、使用量和錯誤資料，以瞭解 Teams 和商務用 Skype 的使用情況和問題，以便計畫產品改進。
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651224"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="aba06-103">商務用 Skype 和 Microsoft Teams 資料收集做法</span><span class="sxs-lookup"><span data-stu-id="aba06-103">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="aba06-104">商務用 Skype Server 和商務用 Skype Online 以及商務用 Skype 和 Microsoft Teams 應用程式收集資料，説明 Microsoft 瞭解這些產品的使用方式以及發生了哪些類型的錯誤，例如登入錯誤。</span><span class="sxs-lookup"><span data-stu-id="aba06-104">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="aba06-105">此資訊可協助我們瞭解使用模式、計畫新功能，以及疑難排解和解決問題區域。</span><span class="sxs-lookup"><span data-stu-id="aba06-105">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="aba06-106">雖然某些使用量資料是自動收集的，但其他資料只能在管理員和/或使用者選擇允許時收集。</span><span class="sxs-lookup"><span data-stu-id="aba06-106">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="aba06-107">資料收集分為以下三類：</span><span class="sxs-lookup"><span data-stu-id="aba06-107">Data collection falls into these three categories:</span></span>

- <span data-ttu-id="aba06-108">人口普查資料</span><span class="sxs-lookup"><span data-stu-id="aba06-108">Census data</span></span>

- <span data-ttu-id="aba06-109">使用量資料</span><span class="sxs-lookup"><span data-stu-id="aba06-109">Usage data</span></span>

- <span data-ttu-id="aba06-110">錯誤報告資料</span><span class="sxs-lookup"><span data-stu-id="aba06-110">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="aba06-111">人口普查資料</span><span class="sxs-lookup"><span data-stu-id="aba06-111">Census data</span></span>

<span data-ttu-id="aba06-112">獲取人口普查資料完全是為了提供、支援和改進商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="aba06-112">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="aba06-113">Microsoft Teams 和商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="aba06-113">Microsoft Teams, and Skype for Business Online.</span></span> <span data-ttu-id="aba06-114">它包括環境資訊，如裝置和作業系統版本，以及區域和語言設置。</span><span class="sxs-lookup"><span data-stu-id="aba06-114">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="aba06-115">它還包括用於登入嘗試和失敗的計數器。</span><span class="sxs-lookup"><span data-stu-id="aba06-115">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="aba06-116">以下是收集的人口普查資料的一些具體示例：</span><span class="sxs-lookup"><span data-stu-id="aba06-116">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="aba06-117">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="aba06-117">**Data type**</span></span>|<span data-ttu-id="aba06-118">**示例**</span><span class="sxs-lookup"><span data-stu-id="aba06-118">**Example**</span></span>|<span data-ttu-id="aba06-119">**注釋**</span><span class="sxs-lookup"><span data-stu-id="aba06-119">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aba06-120">AppName</span><span class="sxs-lookup"><span data-stu-id="aba06-120">AppName</span></span>  <br/> |<span data-ttu-id="aba06-121">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="aba06-121">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="aba06-122">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="aba06-122">DeviceModel</span></span>  <br/> |<span data-ttu-id="aba06-123">iPhone</span><span class="sxs-lookup"><span data-stu-id="aba06-123">iPhone</span></span>  <br/> ||
|<span data-ttu-id="aba06-124">OSName</span><span class="sxs-lookup"><span data-stu-id="aba06-124">OSName</span></span>  <br/> |<span data-ttu-id="aba06-125">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="aba06-125">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="aba06-126">OSVersion</span><span class="sxs-lookup"><span data-stu-id="aba06-126">OSVersion</span></span>  <br/> |<span data-ttu-id="aba06-127">8.3</span><span class="sxs-lookup"><span data-stu-id="aba06-127">8.3</span></span>  <br/> ||
|<span data-ttu-id="aba06-128">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="aba06-128">UserLanguage</span></span>  <br/> |<span data-ttu-id="aba06-129">EN-US</span><span class="sxs-lookup"><span data-stu-id="aba06-129">EN-US</span></span>  <br/> ||
|<span data-ttu-id="aba06-130">UserID</span><span class="sxs-lookup"><span data-stu-id="aba06-130">UserID</span></span>  <br/> |<span data-ttu-id="aba06-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="aba06-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="aba06-132">這個識別碼被散列兩次：一次在用戶端上，一次在遙測服務上。</span><span class="sxs-lookup"><span data-stu-id="aba06-132">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="aba06-133">散列可確保識別碼無法連結到特定使用者。</span><span class="sxs-lookup"><span data-stu-id="aba06-133">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="aba06-134">DeviceID</span><span class="sxs-lookup"><span data-stu-id="aba06-134">DeviceID</span></span>  <br/> |<span data-ttu-id="aba06-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="aba06-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="aba06-136">裝置識別碼是在裝置上隨機生成一次並發送到遙測服務的 GUID。</span><span class="sxs-lookup"><span data-stu-id="aba06-136">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="aba06-137">人口普查資料不包含任何標識你的組織或使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="aba06-137">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="aba06-138">有關詳細資訊，請參閱 [商務用 Skype 隱私權聲明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="aba06-138">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="aba06-139">人口普查資料在預設情況下處於開啟狀態，管理員或最終使用者無法將其關閉。</span><span class="sxs-lookup"><span data-stu-id="aba06-139">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="aba06-140">使用量資料</span><span class="sxs-lookup"><span data-stu-id="aba06-140">Usage data</span></span>

<span data-ttu-id="aba06-141">使用量資料包括諸如呼叫次數、傳送或接收的 IM 數量、加入的會議數量、使用的功能的頻率以及穩定性問題等資訊。</span><span class="sxs-lookup"><span data-stu-id="aba06-141">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="aba06-142">使用量資料中可能包含標識你的組織的資訊，如 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="aba06-142">Usage data might contain information that identifies your organization, such as contoso.com.</span></span> <span data-ttu-id="aba06-143">以下是收集的使用量資料的一些具體示例：</span><span class="sxs-lookup"><span data-stu-id="aba06-143">Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="aba06-144">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="aba06-144">**Data type**</span></span>|<span data-ttu-id="aba06-145">**示例**</span><span class="sxs-lookup"><span data-stu-id="aba06-145">**Example**</span></span>|<span data-ttu-id="aba06-146">**注釋**</span><span class="sxs-lookup"><span data-stu-id="aba06-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aba06-147">發送的即時訊息</span><span class="sxs-lookup"><span data-stu-id="aba06-147">IM Sent</span></span>  <br/> |<span data-ttu-id="aba06-148">12</span><span class="sxs-lookup"><span data-stu-id="aba06-148">12</span></span>  <br/> ||
|<span data-ttu-id="aba06-149">已接收即時訊息</span><span class="sxs-lookup"><span data-stu-id="aba06-149">IM Received</span></span>  <br/> |<span data-ttu-id="aba06-150">5</span><span class="sxs-lookup"><span data-stu-id="aba06-150">5</span></span>  <br/> ||
|<span data-ttu-id="aba06-151">加入會議 (嘗試)</span><span class="sxs-lookup"><span data-stu-id="aba06-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="aba06-152">5</span><span class="sxs-lookup"><span data-stu-id="aba06-152">5</span></span>  <br/> ||
|<span data-ttu-id="aba06-153">加入會議 (成功)</span><span class="sxs-lookup"><span data-stu-id="aba06-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="aba06-154">4</span><span class="sxs-lookup"><span data-stu-id="aba06-154">4</span></span>  <br/> ||
|<span data-ttu-id="aba06-155">通話/會議紀要</span><span class="sxs-lookup"><span data-stu-id="aba06-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="aba06-156">30 分鐘</span><span class="sxs-lookup"><span data-stu-id="aba06-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="aba06-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="aba06-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="aba06-158">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="aba06-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="aba06-159">這是在 Office 365 中註冊的組織的名稱，以明文形式傳輸，這意味著它沒有被模糊處理。</span><span class="sxs-lookup"><span data-stu-id="aba06-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="aba06-160">使用量資料不包含任何標識使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="aba06-160">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="aba06-161">預設情況下，使用量資料收集處於開啟狀態，但本地管理員可以使用商務用 Skype Server 上的 DisableAutomaticSendTracing 群組原則設定將其關閉。</span><span class="sxs-lookup"><span data-stu-id="aba06-161">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="aba06-162">關閉此設定將影響組織中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="aba06-162">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="aba06-163">有關詳細資訊，請參閱[設定用戶端載入原則](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)。</span><span class="sxs-lookup"><span data-stu-id="aba06-163">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="aba06-164">最終使用者無法啟用或停用使用量資料收集。</span><span class="sxs-lookup"><span data-stu-id="aba06-164">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="aba06-165">對於 Skype 會議應用程式和 Join Launcher 網頁，控制遙測的方法是通過以下原則：</span><span class="sxs-lookup"><span data-stu-id="aba06-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="aba06-166">此原則預設為 false，因此預設情況下遙測收集處於關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="aba06-166">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="aba06-167">此設定為每個池，並控制將 Skype 會議應用程式連線至該伺服器上主持的會議的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="aba06-167">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="aba06-168">錯誤報告資料</span><span class="sxs-lookup"><span data-stu-id="aba06-168">Error reporting data</span></span>

<span data-ttu-id="aba06-169">錯誤報告資料可包含有關性能和可靠性、裝置設定、網路連線品質、錯誤碼、錯誤記錄和例外的資訊。</span><span class="sxs-lookup"><span data-stu-id="aba06-169">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="aba06-170">以下是收集的錯誤報告資料的一些具體示例：</span><span class="sxs-lookup"><span data-stu-id="aba06-170">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="aba06-171">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="aba06-171">**Data type**</span></span>|<span data-ttu-id="aba06-172">**示例**</span><span class="sxs-lookup"><span data-stu-id="aba06-172">**Example**</span></span>|<span data-ttu-id="aba06-173">**注釋**</span><span class="sxs-lookup"><span data-stu-id="aba06-173">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aba06-174">訊息方向</span><span class="sxs-lookup"><span data-stu-id="aba06-174">Message direction</span></span>  <br/> |<span data-ttu-id="aba06-175">傳入</span><span class="sxs-lookup"><span data-stu-id="aba06-175">Incoming</span></span>  <br/> ||
|<span data-ttu-id="aba06-176">交談狀態</span><span class="sxs-lookup"><span data-stu-id="aba06-176">Conversation state</span></span>  <br/> |<span data-ttu-id="aba06-177">空閒</span><span class="sxs-lookup"><span data-stu-id="aba06-177">Idle</span></span>  <br/> ||
|<span data-ttu-id="aba06-178">交談執行緒識別碼</span><span class="sxs-lookup"><span data-stu-id="aba06-178">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="aba06-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span><span class="sxs-lookup"><span data-stu-id="aba06-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="aba06-180">UserID</span><span class="sxs-lookup"><span data-stu-id="aba06-180">UserID</span></span>  <br/> |<span data-ttu-id="aba06-181">amosmarble</span><span class="sxs-lookup"><span data-stu-id="aba06-181">amosmarble</span></span> <br/> |<span data-ttu-id="aba06-182">識別碼以明文形式傳送，遙測服務在儲存它之前對其進行雜湊處理</span><span class="sxs-lookup"><span data-stu-id="aba06-182">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="aba06-183">錯誤報告資料還可能包含個人身份資訊，例如使用者的 IP 位址和工作階段初始通訊協定統一資源識別項 (SIP URI)。</span><span class="sxs-lookup"><span data-stu-id="aba06-183">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="aba06-184">有關所收集內容的詳細說明，請參閱 [商務用 Skype 隱私權聲明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="aba06-184">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="aba06-185">錯誤報告需要兩個事項：</span><span class="sxs-lookup"><span data-stu-id="aba06-185">Error reporting requires two things:</span></span>

- <span data-ttu-id="aba06-186">在伺服器或租用戶系統管理中心中，DisableAutomaticSendTracing 群組原則設定設定為 False (這是預設狀態)。</span><span class="sxs-lookup"><span data-stu-id="aba06-186">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="aba06-187">有關詳細資訊，請參閱[設定用戶端載入原則](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)。</span><span class="sxs-lookup"><span data-stu-id="aba06-187">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="aba06-188">最終使用者從 Skype for Business 用戶端的 [一般] 索引標籤 (按一下齒輪圖示![代表齒輪的圖示](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)，然後 **[選項]** 對話方塊開啟並顯示 **[一般]** 索引標簽) 單獨選擇加入。</span><span class="sxs-lookup"><span data-stu-id="aba06-188">End users individually opt in from the General tab (click the gear icon ![An icon that represents a gear ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![[選項] 對話方塊中 [資料收集] 核取方塊的螢幕截圖](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="aba06-190">對於 Skype 會議應用，MeetingUxEnableTelemetry 還控制錯誤報告，不過對於 Windows 上當機，Watson 設定控制上傳當機資訊。</span><span class="sxs-lookup"><span data-stu-id="aba06-190">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="aba06-191">Skype 會議應用程式沒有您在 [桌面用戶端] 對話方塊中看到的使用者設定。</span><span class="sxs-lookup"><span data-stu-id="aba06-191">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="aba06-192">有關詳細資訊，請參閱 [在商務用 Skype 中設定一般選項](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)。</span><span class="sxs-lookup"><span data-stu-id="aba06-192">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="aba06-193">您可以參閱[為商務用 Skype Online 設定網路](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)以設定網路。</span><span class="sxs-lookup"><span data-stu-id="aba06-193">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="aba06-194">如果您在中國使用由世紀互聯運營的 Microsoft 365 或 Office 365，請參閱[為世紀互聯運營的商務用 Skype Online 設定網路](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)。</span><span class="sxs-lookup"><span data-stu-id="aba06-194">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="aba06-195">相關主題</span><span class="sxs-lookup"><span data-stu-id="aba06-195">Related topics</span></span>
[<span data-ttu-id="aba06-196">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="aba06-196">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
