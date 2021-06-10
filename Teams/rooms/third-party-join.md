---
title: 啟用Teams 會議室裝置加入協力廠商會議
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
description: 本文討論如何設定您的組織和Teams 會議室裝置，以支援協力廠商會議加入 Cisco WebEx 和縮放。
ms.openlocfilehash: ef14d1f342c6f2b34ad7c948a2688fa39a09801d
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796687"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>啟用Teams會議室裝置加入協力廠商會議

Microsoft Teams 會議室裝置支援一鍵式體驗，可加入協力廠商線上會議，也稱為直接來賓加入。 啟用時，您可以使用Teams 會議室裝置加入在 Cisco WebEx 和 Zoom 上主持的會議，就像加入在 Microsoft Teams 中主持的會議一樣。

在從裝置Teams 會議室協力廠商會議之前，您必須執行下列操作：

1. 設定Teams 會議室裝置Exchange Online會議室信箱，以處理協力廠商會議邀請。
2. 請確定貴組織沒有任何可阻止您連接到協力廠商會議服務的政策。
3. 設定您的Teams 會議室裝置以允許協力廠商會議。

下列各節將說明如何執行這些步驟。

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>步驟 1：允許處理協力廠商會議的日曆邀請

若要從小組會議室裝置啟用一鍵式加入體驗，您要做的第一件事是設定裝置在會議室信箱Exchange Online規則。 會議室信箱必須允許外部會議，並保留郵件內文和主體，以便查看加入協力廠商會議所需的 URL。 若要使用 [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) Cmdlet 設定這些會議室信箱選項，請執行下列操作：

1. 連線 PowerShell Exchange Online PowerShell。 若要詳細資訊，請參閱連線Exchange Online [PowerShell，](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)或連線Exchange Online多重要素驗證使用[PowerShell，](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)取決於您的驗證方法。

2. 執行下列命令 (，) 取得會議室信箱的 UPN 使用者主體名稱：

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. 尋找與裝置關聯的會議室信箱Teams 會議室，並記下其 UPN。

4. 找到會議室信箱的 UPN 之後，請執行下列命令。 以 `<UserPrincipalName>` 會議室信箱的 UPN 取代：

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

深入瞭解[PowerShell Exchange Online PowerShell。](/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>步驟 2：設定Office 365威脅防護和連結重寫

若要啟用一鍵式加入體驗，協力廠商會議的會議加入連結資訊必須列于會議邀請中，且可讀取。 如果貴組織使用[Office 365 進](/microsoft-365/security/office-365-security/atp-safe-links)一步威脅防護安全連結功能，或者如果您使用協力廠商解決方案來掃描所有傳入和外發 URL 以尋找威脅，則可能會變更會議加入 URL，讓 Teams 會議室 裝置無法辨識會議。 若要確保不會發生此情況，您必須將協力廠商會議服務的 URL 新增到 ATP 安全連結「請勿重寫」清單或協力廠商 URL 重寫例外清單。

若要新增協力廠商會議服務 URL 至 ATP 安全連結 「請勿重寫」清單，請遵循使用 [ATP](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)安全連結設定自訂不重寫 URL 清單中的步驟。 如果您使用協力廠商解決方案，請參閱該解決方案在 URL 重寫例外清單中新增 URL 的指示。

以下是一些您可能需要新增到 ATP 安全連結 「請勿重寫」清單或協力廠商 URL 重寫例外清單的範例專案：

- **Cisco WebEx**`*.webex.com*`
- **縮放** `*.zoom.us*` 、 `*.zoom.com*` 、 `*.zoomgov.com*`

若要將完整的 URL 清單新加到 ATP 安全連結「請勿重寫」清單或協力廠商 URL 重寫例外清單，請連上您想要接受會議邀請的協力廠商會議服務提供者。 

> [!CAUTION]
> 只新增您信任的 URL 到 ATP 安全連結「請勿重寫」清單或協力廠商 URL 重寫例外清單。

## <a name="step-3-enable-third-party-meetings-on-device"></a>步驟 3：在裝置上啟用協力廠商會議

您需要執行的最後一個步驟是允許每個Teams 會議室裝置加入協力廠商會議。 協力廠商會議需要使用者名稱和電子郵件地址來加入。 如果您所需的使用者名稱和電子郵件地址與裝置會議室信箱不同，您必須將它們新加入您的裝置。 您可以在裝置設定或 XML 設定檔中執行此操作。

### <a name="use-device-settings"></a>使用裝置設定

若要使用Teams 會議室來設定裝置，請執行下列操作：

1. 在裝置Microsoft Teams 會議室，選取更多 **...**。
2. 選取 **設定**，然後輸入裝置系統管理員的使用者名稱和密碼。
3. 請前往會議 **索引** 點，然後選取 **Cisco WebEx、****縮放** 或兩者。
4. 如果您想要使用與會議室信箱相關聯的使用者名稱和電子郵件地址加入會議，請選取使用會議室資訊 **加入**。
5. 如果您想要使用替代使用者名稱和電子郵件地址加入會議，請選取使用自訂資訊加入，然後輸入您想要使用的使用者名稱和電子郵件地址。
6. 選取 **儲存並離開**。 您的裝置將會重新開機。

### <a name="use-the-skypesettingsxml-configuration-file"></a>使用 SkypeSettings.xml組設定檔

您可以新增下列設定至位於 中的 `SkypeSettings.xml` 檔案 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。 有關檔案詳細資訊，請參閱使用 XML 設定檔Microsoft Teams 會議室 `SkypeSettings.xml` [管理主機設定](xml-config-file.md)。

若要啟用 Cisco WebEx 會議，請設定 `WebExMeetingsEnabled` XML 元素為 **True，** 如下所示。

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

若要啟用縮放會議，請設定 `ZoomMeetingsEnabled` XML 元素為 **True，** 如下所示。

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

您可以選擇地指定自訂使用者名稱和電子郵件地址，以使用下列 XML 元素加入協力廠商會議。 如果您提供的值無效，Teams 會議室預設會使用會議室信箱使用者名稱和電子郵件地址。

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> 若要從 Teams 會議室 裝置加入 Cisco WebEx 會議，Cisco 會議必須以 WebEx 會議Pro使用 Cisco WebEx Web 應用程式版本 WBS 40.7 或更新版本進行。 
