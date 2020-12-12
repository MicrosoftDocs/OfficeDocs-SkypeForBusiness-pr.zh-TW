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
ms.openlocfilehash: 8079b6fc231bf30a654e2513af55a806433eb83f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662358"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>啟用團隊聊天室裝置以加入協力廠商會議

Microsoft 團隊會議室裝置支援加入協力廠商線上會議的單一觸控體驗。 啟用時，您可以使用小組聊天室裝置加入在 Cisco WebEx 和縮放比例上託管的會議，就像您加入在 Microsoft 團隊中主持的<sup>會議一樣輕鬆</sup> 。

您必須先執行下列動作，才能從團隊聊天室裝置加入協力廠商會議：

1. 設定團隊聊天室裝置的 Exchange Online 聊天室信箱，以處理協力廠商會議的邀請
2. 確定貴組織沒有任何原則可讓您無法連線至協力廠商會議服務
3. 設定團隊室裝置以允許協力廠商會議

下列各節說明如何執行這些步驟。

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>步驟1：允許協力廠商會議的行事曆邀請處理

若要從團隊聊天室裝置啟用單一觸控的連線體驗，您必須先設定該裝置的 Exchange Online 聊天室信箱的行事曆處理規則。 會議室信箱必須允許外部會議，並保留郵件的正文和主旨，讓它可以看到加入協力廠商會議所需的 URL。 若要使用 [CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) Cmdlet 設定這些會議室信箱選項，請執行下列動作：

1. [連線至 Exchange Online PowerShell]。 如需詳細資訊，請參閱使用 [基本驗證連線至 Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) ，或 [使用多重要素驗證連線至 exchange online powershell](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)（視您的驗證方法而定）。

2. 如果您不知道它是透過執行下列命令，就能取得會議室信箱 (UPN) 的使用者主要名稱：

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. 尋找與您的小組聊天室裝置相關聯的聊天室信箱名稱，並記下其 UPN

4. 找到聊天室信箱的 UPN 之後，請執行下列命令。 取代 `<UserPrincipalName>` 為會議室信箱的 UPN：

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

深入瞭解 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)。

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>步驟2：設定 Office 365 威脅防護與連結重寫

若要啟用單一觸控式連接體驗，來自協力廠商會議的會議加入連結資訊必須在會議邀請中出現且可供閱讀。 如果您的組織使用的是 [Office 365 高級威脅防護安全連結](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) 功能，或您使用協力廠商解決方案來掃描所有內送及外寄的威脅，可能會變更會議加入 url，並讓小組聊天室裝置無法使用該會議。 若要確保不會發生這種情況，您需要將協力廠商會議服務的 Url 新增至 ATP 安全連結「不要重新寫入」清單或協力廠商 URL 重寫例外清單。

若要將協力廠商會議服務 Url 新增至 ATP 安全連結「不要重新寫入」清單中，請依照 [使用 ATP 安全連結設定自訂的 [不重寫] url 清單](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)中的步驟進行。 如果您使用的是協力廠商解決方案，請參閱該方案的指示，以將 Url 新增到其 URL 重寫例外清單中。

以下是一些您可能需要新增至 ATP 安全連結「不要重新寫入」清單或協力廠商 URL 重寫例外清單的範例專案：

- **Cisco WebEx**`*.webex.com*`
- **縮放** `*.zoom.us*` 、 `*.zoom.com*``*.zoomgov.com*`

若要將完整的 Url 清單新增至您的 ATP 安全連結「不要重新寫入」清單或協力廠商 URL 重寫例外清單，請與您想要接受會議邀請的協力廠商會議服務提供者聯繫。 

> [!CAUTION]
> 僅將您信任的 Url 新增到您的 ATP 安全連結「不要重新寫入」清單或協力廠商 URL 重寫例外清單。

## <a name="step-3-enable-third-party-meetings-on-device"></a>步驟3：在裝置上啟用協力廠商會議

您需要執行的最後一個步驟是允許每個團隊聊天室裝置加入協力廠商會議。 協力廠商會議需要使用者名稱和電子郵件地址才能加入它們。 如果您需要使用的使用者名稱和電子郵件地址與裝置的會議室信箱不同，您必須將它們新增至您的裝置。 您可以在 [裝置設定] 或 XML 設定檔中執行此動作。

### <a name="use-device-settings"></a>使用裝置設定

若要使用觸控式螢幕設定團隊聊天室裝置，請執行下列動作：

1. 在 Microsoft 團隊聊天室裝置上，選取 [**更多 ...** ]。
2. 選取 [ **設定**]，然後輸入裝置管理員的使用者名稱和密碼
3. 移至 [ **會議** ] 索引標籤，然後選取 [ **Cisco WebEx**]、[ **縮放比例**<sup>1</sup>] 或兩者
4. 如果您想要使用與會議室信箱相關聯的使用者名稱和電子郵件地址來加入會議，請選取 [**加入會議室資訊**]
5. 如果您想要使用替代的使用者名稱和電子郵件地址加入會議，請選取 [ **加入自訂資訊** ]，然後輸入您想要使用的使用者名稱和電子郵件地址。
6. 選取 [ **儲存並** 結束]。 您的裝置將會重新開機。

### <a name="use-the-skypesettingsxml-configuration-file"></a>使用 SkypeSettings.xml 設定檔

您可以將下列設定新增至 `SkypeSettings.xml` 位於中的檔案 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。 如需檔案的詳細資訊 `SkypeSettings.xml` ，請參閱 [使用 XML 設定檔遠端系統管理 Microsoft 團隊聊天室的主控台設定](xml-config-file.md)。

若要啟用 Cisco WebEx 會議，請將 `WebExMeetingsEnabled` XML 元素設定為 **True**，如下所示。

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

若要啟用 [縮放 <sup>1</sup> ] 會議，請將 `ZoomMeetingsEnabled` XML 元素設定為 **True**，如下所示。

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

您也可以選擇指定自訂的使用者名稱和電子郵件地址，以使用下列 XML 元素加入協力廠商會議。 如果您提供的值無效，小組聊天室裝置將預設為使用會議室信箱的使用者名稱和電子郵件地址。

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> 若要從團隊聊天室裝置加入 Cisco WebEx 會議，必須使用 Cisco WebEx web 應用程式版本 WBS 40.7 或更新版本來託管 Cisco 會議。

<sup>1</sup> [縮放會議] 目前只有透過技術存取計畫來選取 Microsoft 團隊聊天室客戶 (輕觸) 。
