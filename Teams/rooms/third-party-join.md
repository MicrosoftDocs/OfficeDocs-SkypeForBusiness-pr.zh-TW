---
title: 啟用團隊聊天室裝置以加入協力廠商會議
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
description: 本文將討論如何設定您的組織和小組聊天室裝置，以支援加入 Cisco WebEx 和縮放的協力廠商會議。
ms.openlocfilehash: 82369c534a616796382b1de69e37c64f15392f9b
ms.sourcegitcommit: db0dc45520503753567e99c0c016f0265d45aa66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682382"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="b1197-103">啟用團隊聊天室裝置以加入協力廠商會議</span><span class="sxs-lookup"><span data-stu-id="b1197-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="b1197-104">Microsoft 團隊會議室裝置支援加入協力廠商線上會議的單一觸控體驗，也稱為直接來賓加入。</span><span class="sxs-lookup"><span data-stu-id="b1197-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="b1197-105">啟用時，您可以使用小組聊天室裝置加入在 Cisco WebEx 和縮放中託管的會議，就像您加入託管于 Microsoft 團隊中的會議一樣輕鬆。</span><span class="sxs-lookup"><span data-stu-id="b1197-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="b1197-106">您必須先執行下列動作，才能從團隊聊天室裝置加入協力廠商會議：</span><span class="sxs-lookup"><span data-stu-id="b1197-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="b1197-107">設定團隊聊天室裝置的 Exchange Online 聊天室信箱，以處理協力廠商會議的邀請。</span><span class="sxs-lookup"><span data-stu-id="b1197-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="b1197-108">請確定貴組織沒有任何原則可讓您無法連線至協力廠商會議服務。</span><span class="sxs-lookup"><span data-stu-id="b1197-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="b1197-109">將您的小組室裝置設定為允許協力廠商會議。</span><span class="sxs-lookup"><span data-stu-id="b1197-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="b1197-110">下列各節說明如何執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="b1197-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="b1197-111">步驟1：允許協力廠商會議的行事曆邀請處理</span><span class="sxs-lookup"><span data-stu-id="b1197-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="b1197-112">若要從團隊聊天室裝置啟用單一觸控的連線體驗，您必須先設定該裝置的 Exchange Online 聊天室信箱的行事曆處理規則。</span><span class="sxs-lookup"><span data-stu-id="b1197-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="b1197-113">會議室信箱必須允許外部會議，並保留郵件的正文和主旨，讓它可以看到加入協力廠商會議所需的 URL。</span><span class="sxs-lookup"><span data-stu-id="b1197-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="b1197-114">若要使用 [CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) Cmdlet 設定這些會議室信箱選項，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b1197-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="b1197-115">[連線至 Exchange Online PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="b1197-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="b1197-116">如需詳細資訊，請參閱使用 [基本驗證連線至 Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) ，或 [使用多重要素驗證連線至 exchange online powershell](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)（視您的驗證方法而定）。</span><span class="sxs-lookup"><span data-stu-id="b1197-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="b1197-117">如果您不知道它是透過執行下列命令，就能取得會議室信箱 (UPN) 的使用者主要名稱：</span><span class="sxs-lookup"><span data-stu-id="b1197-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="b1197-118">尋找與您的小組聊天室裝置相關聯的聊天室信箱名稱，並記下其 UPN。</span><span class="sxs-lookup"><span data-stu-id="b1197-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="b1197-119">找到聊天室信箱的 UPN 之後，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="b1197-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="b1197-120">取代 `<UserPrincipalName>` 為會議室信箱的 UPN：</span><span class="sxs-lookup"><span data-stu-id="b1197-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="b1197-121">深入瞭解 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="b1197-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="b1197-122">步驟2：設定 Office 365 威脅防護與連結重寫</span><span class="sxs-lookup"><span data-stu-id="b1197-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="b1197-123">若要啟用單一觸控式連接體驗，來自協力廠商會議的會議加入連結資訊必須在會議邀請中出現且可供閱讀。</span><span class="sxs-lookup"><span data-stu-id="b1197-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="b1197-124">如果您的組織使用的是 [Office 365 高級威脅防護安全連結](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) 功能，或您使用協力廠商解決方案來掃描所有內送及外寄的威脅，可能會變更會議加入 url，並讓小組聊天室裝置無法使用該會議。</span><span class="sxs-lookup"><span data-stu-id="b1197-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="b1197-125">若要確保不會發生這種情況，您需要將協力廠商會議服務的 Url 新增至 ATP 安全連結「不要重新寫入」清單或協力廠商 URL 重寫例外清單。</span><span class="sxs-lookup"><span data-stu-id="b1197-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="b1197-126">若要將協力廠商會議服務 Url 新增至 ATP 安全連結「不要重新寫入」清單中，請依照 [使用 ATP 安全連結設定自訂的 [不重寫] url 清單](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="b1197-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="b1197-127">如果您使用的是協力廠商解決方案，請參閱該方案的指示，以將 Url 新增到其 URL 重寫例外清單中。</span><span class="sxs-lookup"><span data-stu-id="b1197-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="b1197-128">以下是一些您可能需要新增至 ATP 安全連結「不要重新寫入」清單或協力廠商 URL 重寫例外清單的範例專案：</span><span class="sxs-lookup"><span data-stu-id="b1197-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="b1197-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="b1197-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="b1197-130">**縮放** `*.zoom.us*` 、 `*.zoom.com*``*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="b1197-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="b1197-131">若要將完整的 Url 清單新增至您的 ATP 安全連結「不要重新寫入」清單或協力廠商 URL 重寫例外清單，請與您想要接受會議邀請的協力廠商會議服務提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="b1197-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="b1197-132">僅將您信任的 Url 新增到您的 ATP 安全連結「不要重新寫入」清單或協力廠商 URL 重寫例外清單。</span><span class="sxs-lookup"><span data-stu-id="b1197-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="b1197-133">步驟3：在裝置上啟用協力廠商會議</span><span class="sxs-lookup"><span data-stu-id="b1197-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="b1197-134">您需要執行的最後一個步驟是允許每個團隊聊天室裝置加入協力廠商會議。</span><span class="sxs-lookup"><span data-stu-id="b1197-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="b1197-135">協力廠商會議需要使用者名稱和電子郵件地址才能加入它們。</span><span class="sxs-lookup"><span data-stu-id="b1197-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="b1197-136">如果您需要使用的使用者名稱和電子郵件地址與裝置的會議室信箱不同，您必須將它們新增至您的裝置。</span><span class="sxs-lookup"><span data-stu-id="b1197-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="b1197-137">您可以在 [裝置設定] 或 XML 設定檔中執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b1197-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="b1197-138">使用裝置設定</span><span class="sxs-lookup"><span data-stu-id="b1197-138">Use device settings</span></span>

<span data-ttu-id="b1197-139">若要使用觸控式螢幕設定團隊聊天室裝置，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b1197-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="b1197-140">在 Microsoft 團隊聊天室裝置上，選取 [ **更多 ...**]。</span><span class="sxs-lookup"><span data-stu-id="b1197-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="b1197-141">選取 [ **設定**]，然後輸入裝置管理員的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="b1197-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="b1197-142">移至 [ **會議** ] 索引標籤，然後選取 [ **Cisco WebEx**]、[ **縮放**] 或兩者。</span><span class="sxs-lookup"><span data-stu-id="b1197-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="b1197-143">如果您想要使用與會議室信箱相關聯的使用者名稱和電子郵件地址來加入會議，請選取 [ **加入會議室資訊**]。</span><span class="sxs-lookup"><span data-stu-id="b1197-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="b1197-144">如果您想要使用替代的使用者名稱和電子郵件地址加入會議，請選取 [ **加入自訂資訊** ]，然後輸入您想要使用的使用者名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b1197-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="b1197-145">選取 [ **儲存並** 結束]。</span><span class="sxs-lookup"><span data-stu-id="b1197-145">Select **Save and exit**.</span></span> <span data-ttu-id="b1197-146">您的裝置將會重新開機。</span><span class="sxs-lookup"><span data-stu-id="b1197-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="b1197-147">使用 SkypeSettings.xml 設定檔</span><span class="sxs-lookup"><span data-stu-id="b1197-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="b1197-148">您可以將下列設定新增至 `SkypeSettings.xml` 位於中的檔案 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。</span><span class="sxs-lookup"><span data-stu-id="b1197-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="b1197-149">如需檔案的詳細資訊 `SkypeSettings.xml` ，請參閱 [使用 XML 設定檔遠端系統管理 Microsoft 團隊聊天室的主控台設定](xml-config-file.md)。</span><span class="sxs-lookup"><span data-stu-id="b1197-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="b1197-150">若要啟用 Cisco WebEx 會議，請將 `WebExMeetingsEnabled` XML 元素設定為 **True**，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b1197-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="b1197-151">若要啟用 [縮放會議]，請將 `ZoomMeetingsEnabled` XML 元素設定為 **True**，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b1197-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="b1197-152">您也可以選擇指定自訂的使用者名稱和電子郵件地址，以使用下列 XML 元素加入協力廠商會議。</span><span class="sxs-lookup"><span data-stu-id="b1197-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="b1197-153">如果您提供的值無效，小組聊天室裝置將預設為使用會議室信箱的使用者名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b1197-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="b1197-154">若要從團隊聊天室裝置加入 Cisco WebEx 會議，必須使用 Cisco WebEx web 應用程式版本 WBS 40.7 或更新版本來託管 Cisco 會議。</span><span class="sxs-lookup"><span data-stu-id="b1197-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

