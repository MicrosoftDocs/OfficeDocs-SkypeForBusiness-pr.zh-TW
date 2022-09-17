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
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 本文討論如何設定貴組織及Teams 會議室裝置，以支援加入 Cisco Webex 和 Zoom 的協力廠商會議。
ms.openlocfilehash: 70d2cf03dea3fcfef3d08c07f4f771bd8a2ea70e
ms.sourcegitcommit: 89e3681a88f06a9c6860d9eaea598e57b928b68a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2022
ms.locfileid: "67794992"
---
# <a name="enable-teams-rooms-devices-to-join-third-party-meetings"></a>啟用Teams 會議室裝置加入協力廠商會議

Microsoft Teams 會議室裝置支援加入協力廠商線上會議的單點觸控體驗，也稱為直接來賓加入。 啟用時，您可以使用Teams 會議室加入 Cisco Webex 上託管的會議，以及使用 Zoom，就像加入在 Microsoft Teams 中主持的會議一樣輕鬆。

支援的裝置和服務：

- Teams 會議室在 Windows 上，所有通過認證的型號 – 縮放、Cisco Webex

- Teams 會議室在 Android 上，所有通過認證的型號 – 縮放、Cisco Webex

    > [!NOTE]
    > Microsoft 會定期在 Android 上發行Teams 會議室的新功能。 不過，在功能發行時間與在裝置上推出功能之間可能會有延遲。 如果裝置上無法使用某項功能，請洽詢裝置製造商，以瞭解何時可以使用該功能。

> [!NOTE]
> 若要從Teams 會議室裝置加入 Cisco Webex 會議，Cisco 會議必須使用 Cisco Webex Web 應用程式版本 WBS 40.7 或更新版本託管在 Webex Meetings Pro 中。

在您可以從Teams 會議室加入協力廠商會議之前，您必須執行下列動作：

1. 設定Teams 會議室Exchange Online會議室信箱以處理協力廠商會議的邀請。
2. 請確定貴組織沒有任何原則可防止您連線至協力廠商會議服務。
3. 設定Teams 會議室允許協力廠商會議。

下列各節說明如何完成這些步驟。

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>步驟 1：允許處理協力廠商會議的行事曆邀請

若要從小組會議室啟用單點觸控加入體驗，您必須先設定裝置Exchange Online會議室信箱的行事曆處理規則。 會議室信箱必須允許外部會議，並保留郵件內文和主旨，以便查看加入協力廠商會議所需的 URL。 若要使用 [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing.) Cmdlet 設定這些會議室信箱選項，請執行下列動作：

1. 連線至 Exchange Online PowerShell。 如需詳細資訊，請參閱使用[基本驗證連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)或[使用多重要素驗證連線到 Exchange Online PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell)，視您的驗證方法而定。

2. 如果您不知道會議室信箱的使用者主體名稱 (UPN) ，請執行下列命令：

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. 尋找與Teams 會議室裝置相關聯之聊天室信箱的名稱，並記下其 UPN。

4. 找到會議室信箱的 UPN 之後，請執行下列命令。 使用會議室信箱的 UPN 取代 `<UserPrincipalName>` ：

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

深入瞭解[powerShell Exchange Online](/powershell/exchange/exchange-online-powershell)。

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>步驟 2：設定Office 365威脅防護和連結重寫

若要啟用單點觸控加入體驗，協力廠商會議的會議加入連結資訊必須在會議邀請中呈現並可讀取。 如果您的組織使用[適用於 Office 365 的 Microsoft Defender](/microsoft-365/security/office-365-security/safe-links)安全連結功能，或者如果您使用協力廠商解決方案來掃描所有內送和外寄 URL 的威脅，它可能會變更會議加入 URL，並讓Teams 會議室裝置無法辨識會議。 若要確保這不會發生，您必須將協力廠商會議服務的 URL 新增至 [Defender 以Office 365安全連結 **請勿重寫** 清單](/microsoft-365/security/office-365-security/safe-links)或協力廠商 URL 重寫例外清單。

 如果您使用協力廠商解決方案，請參閱該解決方案的指示，將 URL 新增至 URL 重寫例外清單。

以下是一些您可能需要新增至適用於 Office 365 的 Defender安全連結 *不要重寫* 清單或協力廠商 URL 重寫例外清單的範例專案：

- **Cisco Webex** `*.webex.com/*`
- **[縮放** `*.zoom.us/*` ] 底下， `*.zoom.com/*``*.zoomgov.com/*`

如需要新增至適用於 Office 365 的 Defender安全連結的完整 URL 清單 *請勿重寫* 清單或協力廠商 URL 重寫例外清單，請連絡您要接受會議邀請的協力廠商會議服務提供者。

> [!CAUTION]
> 只將信任的 URL 新增至適用於 Office 365 的 Microsoft Defender安全連結 *請勿重寫* 清單或協力廠商 URL 重寫例外清單。

## <a name="step-3a-enable-third-party-meetings-on-teams-rooms-on-windows"></a>步驟 3a：在 Windows 上啟用 Teams 會議室 上的協力廠商會議

您需要執行的最後一個步驟是允許Teams 會議室加入協力廠商會議。 協力廠商會議需要使用者名稱和電子郵件地址才能加入。 如果您需要使用的使用者名稱和電子郵件地址與裝置的會議室信箱不同，您必須將它們新增至您的裝置。 您可以在Teams 會議室設定或 XML 設定檔案中執行此動作。 您可以在任何功能Teams 會議室的Teams 會議室設定或 Windows 上Teams 會議室的 XML 設定檔案中執行此動作。

### <a name="use-device-settings"></a>使用裝置設定

若要在 Windows 上使用觸控螢幕主機設定Teams 會議室，請執行下列動作：

1. 在Microsoft Teams 會議室主機上，選取 [**更多]**。
2. 選 **取 [設定]**，然後輸入裝置系統管理員的使用者名稱和密碼。
3. 移至 [ **會議]** 索引標籤，然後選取您要啟用 (的協力廠商會議提供者，例如 **Webex**、 **Zoom** 等) 。
4. 如果您想要使用與會議室信箱相關聯的使用者名稱和電子郵件地址加入會議，請選取 [ **使用會議室資訊加入]**。
5. 如果您想要使用備用使用者名稱和電子郵件地址加入會議，請選取 [ **使用自訂資訊** 加入]，然後輸入您要使用的使用者名稱和電子郵件地址。
6. 選 **取 [儲存並結束]**。 您的裝置將會重新開機。

### <a name="use-the-skypesettingsxml-configuration-file"></a>使用SkypeSettings.xml組態檔

下列設定可新增至 `SkypeSettings.xml` 位於中的檔案。 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 如需有關檔案的 `SkypeSettings.xml` 詳細資訊，請參閱[使用 XML 組態檔從遠端系統管理Microsoft Teams 會議室主機設定](xml-config-file.md)。

若要啟用 Cisco Webex 會議，請將 XML 元素設定 `WebexMeetingsEnabled` 為 **True**，如下所示。

```xml
<WebexMeetingsEnabled>True</WebexMeetingsEnabled>
```

若要啟用縮放會議，請將 XML 元素設定 `ZoomMeetingsEnabled` 為 **True**，如下所示。

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

您可以選擇性地指定自訂使用者名稱和電子郵件地址，以使用下列 XML 元素加入協力廠商會議。 如果您提供的值無效，Teams 會議室裝置預設會使用會議室信箱使用者名稱和電子郵件地址。

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```
## <a name="step-3b-enable-third-party-meetings-on-teams-rooms-on-android"></a>步驟 3b：在 Android 上啟用 Teams 會議室 上的協力廠商會議

若要在 Android 上使用觸控螢幕主機或前方顯示器設定Teams 會議室，請執行下列動作：

1.  在Microsoft Teams 會議室主機或會議室前方顯示器上，選取 [**更多]**。
2.  選 **取 [設定]**，然後：
    -   如果使用個人帳戶 (例如具有 E5 授權的帳戶) ，請選擇 **[會議** ] 選項。
    -   例如，如果使用共用帳戶 (，具有Teams 會議室授權的資源帳戶) ，請選擇 **[裝置設定**]、**找出 Teams 管理員設定**、輸入系統管理員密碼，以及選擇 **[會議**] 選項。
      > [!NOTE]
      > 有些裝置製造商需要系統管理員密碼，才能存取 **裝置設定** 。

    ![Android 上 MTR 的會議設定](..\media\mtrandroid.png)

3.  選取您要啟用的協力廠商會議提供者。
4.  如果您想要使用自訂使用者名稱和電子郵件地址加入會議，請選取 [ **使用自訂名稱和電子郵件加入]**。 若要更新自訂個人資訊，請按 **[編輯自訂資訊** ]，並輸入您慣用的名稱和電子郵件地址。

