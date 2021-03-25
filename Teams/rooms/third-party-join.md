---
title: 啟用 Teams 會議室裝置加入協力廠商會議
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文討論如何設定您的組織和 Teams 會議室裝置，以支援協力廠商會議加入 Cisco WebEx 和縮放。
ms.openlocfilehash: c8f6bda7680ccd3107c313c87001902e442518c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117371"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="35b9f-103">啟用 Teams 會議室裝置加入協力廠商會議</span><span class="sxs-lookup"><span data-stu-id="35b9f-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="35b9f-104">Microsoft Teams 會議室裝置支援一鍵式體驗，可加入協力廠商線上會議，也稱為直接來賓加入。</span><span class="sxs-lookup"><span data-stu-id="35b9f-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="35b9f-105">啟用時，您可以使用 Teams 會議室裝置加入在 Cisco WebEx 上主持的會議，並輕鬆縮放，就像加入在 Microsoft Teams 中主持的會議一樣。</span><span class="sxs-lookup"><span data-stu-id="35b9f-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="35b9f-106">在從 Teams 會議室裝置加入協力廠商會議之前，您需要執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="35b9f-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="35b9f-107">設定 Teams 會議室裝置 Exchange Online 會議室信箱，以處理協力廠商會議的邀請。</span><span class="sxs-lookup"><span data-stu-id="35b9f-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="35b9f-108">請確定貴組織沒有任何可阻止您連接到協力廠商會議服務的政策。</span><span class="sxs-lookup"><span data-stu-id="35b9f-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="35b9f-109">設定您的 Teams 會議室裝置以允許協力廠商會議。</span><span class="sxs-lookup"><span data-stu-id="35b9f-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="35b9f-110">下列各節將說明如何執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="35b9f-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="35b9f-111">步驟 1：允許處理協力廠商會議的日曆邀請</span><span class="sxs-lookup"><span data-stu-id="35b9f-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="35b9f-112">若要從小組會議室裝置啟用單鍵加入體驗，您要做的第一件事是設定裝置 Exchange Online 會議室信箱的日曆處理規則。</span><span class="sxs-lookup"><span data-stu-id="35b9f-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="35b9f-113">會議室信箱必須允許外部會議，並保留郵件內文和主體，以便查看加入協力廠商會議所需的 URL。</span><span class="sxs-lookup"><span data-stu-id="35b9f-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="35b9f-114">若要使用 [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) Cmdlet 設定這些會議室信箱選項，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="35b9f-114">To set these room mailbox options using the [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="35b9f-115">連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="35b9f-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="35b9f-116">詳細資訊，請參閱使用基本驗證連線到[Exchange Online PowerShell，](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)或根據您驗證方法使用多重要素驗證連線到[Exchange Online PowerShell。](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="35b9f-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="35b9f-117">執行下列 (，) 取得會議室信箱中的使用者主體名稱：</span><span class="sxs-lookup"><span data-stu-id="35b9f-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="35b9f-118">尋找與 Teams 會議室裝置相關聯的會議室信箱名稱，並記下其 UPN。</span><span class="sxs-lookup"><span data-stu-id="35b9f-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="35b9f-119">找到會議室信箱的 UPN 之後，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="35b9f-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="35b9f-120">以 `<UserPrincipalName>` 會議室信箱的 UPN 取代：</span><span class="sxs-lookup"><span data-stu-id="35b9f-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="35b9f-121">深入瞭解 [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="35b9f-121">Learn more about [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="35b9f-122">步驟 2：設定 Office 365 威脅防護和連結重寫</span><span class="sxs-lookup"><span data-stu-id="35b9f-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="35b9f-123">若要啟用一鍵式加入體驗，協力廠商會議的會議加入連結資訊必須呈現在會議邀請中，且可讀取。</span><span class="sxs-lookup"><span data-stu-id="35b9f-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="35b9f-124">如果貴組織使用 [Office 365](/microsoft-365/security/office-365-security/atp-safe-links) 進一步威脅防護安全連結功能，或如果您使用協力廠商解決方案掃描所有傳入和外發 URL 以尋找威脅，則可能會變更會議加入 URL，讓 Teams 會議室裝置無法辨識會議。</span><span class="sxs-lookup"><span data-stu-id="35b9f-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="35b9f-125">若要確保不會發生此情況，您必須將協力廠商會議服務的 URL 新增到 ATP 安全連結「請勿重寫」清單或協力廠商 URL 重寫例外清單。</span><span class="sxs-lookup"><span data-stu-id="35b9f-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="35b9f-126">若要新增協力廠商會議服務 URL 至 ATP 安全連結「請勿重寫」清單，請遵循使用 [ATP](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)安全連結設定自訂不重寫 URL 清單中的步驟。</span><span class="sxs-lookup"><span data-stu-id="35b9f-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="35b9f-127">如果您使用協力廠商解決方案，請參閱該解決方案在 URL 重寫例外清單中新增 URL 的指示。</span><span class="sxs-lookup"><span data-stu-id="35b9f-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="35b9f-128">以下是一些您可能需要新增到 ATP 安全連結 「請勿重寫」清單或協力廠商 URL 重寫例外清單的範例專案：</span><span class="sxs-lookup"><span data-stu-id="35b9f-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="35b9f-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="35b9f-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="35b9f-130">**縮放** `*.zoom.us*` 、 `*.zoom.com*` 、 `*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="35b9f-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="35b9f-131">若要將完整的 URL 清單新加到 ATP 安全連結「請勿重寫」清單或協力廠商 URL 重寫例外清單，請連上您想要接受會議邀請的協力廠商會議服務提供者。</span><span class="sxs-lookup"><span data-stu-id="35b9f-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="35b9f-132">只新增您信任的 URL 到 ATP 安全連結「請勿重寫」清單或協力廠商 URL 重寫例外清單。</span><span class="sxs-lookup"><span data-stu-id="35b9f-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="35b9f-133">步驟 3：在裝置上啟用協力廠商會議</span><span class="sxs-lookup"><span data-stu-id="35b9f-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="35b9f-134">最後一個步驟是允許每個 Teams 會議室裝置加入協力廠商會議。</span><span class="sxs-lookup"><span data-stu-id="35b9f-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="35b9f-135">協力廠商會議需要使用者名稱和電子郵件地址來加入。</span><span class="sxs-lookup"><span data-stu-id="35b9f-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="35b9f-136">如果您所需的使用者名稱和電子郵件地址與裝置會議室信箱不同，您必須將它們新加入您的裝置。</span><span class="sxs-lookup"><span data-stu-id="35b9f-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="35b9f-137">您可以在裝置設定或 XML 設定檔中執行此操作。</span><span class="sxs-lookup"><span data-stu-id="35b9f-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="35b9f-138">使用裝置設定</span><span class="sxs-lookup"><span data-stu-id="35b9f-138">Use device settings</span></span>

<span data-ttu-id="35b9f-139">若要使用觸控螢幕設定 Teams 會議室裝置，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="35b9f-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="35b9f-140">在 Microsoft Teams 會議室裝置上，選取更多 **...**。</span><span class="sxs-lookup"><span data-stu-id="35b9f-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="35b9f-141">選取 **設定**，然後輸入裝置系統管理員使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="35b9f-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="35b9f-142">前往會議 **索引點**，然後選取 **Cisco WebEx、\*\*\*\*縮放** 或兩者。</span><span class="sxs-lookup"><span data-stu-id="35b9f-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="35b9f-143">如果您想要使用與會議室信箱相關聯的使用者名稱和電子郵件地址加入會議，請選取 **使用會議室資訊加入**。</span><span class="sxs-lookup"><span data-stu-id="35b9f-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="35b9f-144">如果您想要使用替代使用者名稱和電子郵件地址加入會議，請選取使用自訂資訊加入，然後輸入您想要使用的使用者名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="35b9f-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="35b9f-145">選取 **儲存並離開**。</span><span class="sxs-lookup"><span data-stu-id="35b9f-145">Select **Save and exit**.</span></span> <span data-ttu-id="35b9f-146">您的裝置將會重新開機。</span><span class="sxs-lookup"><span data-stu-id="35b9f-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="35b9f-147">使用 SkypeSettings.xml組設定檔</span><span class="sxs-lookup"><span data-stu-id="35b9f-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="35b9f-148">您可以新增下列設定至 `SkypeSettings.xml` 位於 中的檔案 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。</span><span class="sxs-lookup"><span data-stu-id="35b9f-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="35b9f-149">有關檔案詳細資訊，請參閱使用 XML 設定檔遠端系統管理 `SkypeSettings.xml` [Microsoft Teams 會議室主控台設定](xml-config-file.md)。</span><span class="sxs-lookup"><span data-stu-id="35b9f-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="35b9f-150">若要啟用 Cisco WebEx 會議，請設定 `WebExMeetingsEnabled` XML 元素為 **True，** 如下所示。</span><span class="sxs-lookup"><span data-stu-id="35b9f-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="35b9f-151">若要啟用縮放會議，請設定 `ZoomMeetingsEnabled` XML 元素為 **True，** 如下所示。</span><span class="sxs-lookup"><span data-stu-id="35b9f-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="35b9f-152">您可以選擇地指定自訂使用者名稱和電子郵件地址，以使用下列 XML 元素加入協力廠商會議。</span><span class="sxs-lookup"><span data-stu-id="35b9f-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="35b9f-153">如果您提供的值無效，Teams 會議室裝置預設會使用會議室信箱使用者名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="35b9f-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="35b9f-154">若要從 Teams 會議室裝置加入 Cisco WebEx 會議，必須使用 Cisco WebEx Web 應用程式版本 WBS 40.7 或更新版本來主持 Cisco 會議。</span><span class="sxs-lookup"><span data-stu-id="35b9f-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>