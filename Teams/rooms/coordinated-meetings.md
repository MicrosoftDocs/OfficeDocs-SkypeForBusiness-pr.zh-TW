---
title: 使用會議與會議Microsoft Teams 會議室Surface Hub
ms.author: czawideh
author: cazawideh
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 設定Teams 會議室裝置和Surface Hub，以在一或另一個裝置加入會議時加入會議。
ms.openlocfilehash: 5c52b1f6465db57613f45401c425a05286503454
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503700"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>設定具有Microsoft Teams 會議室Surface Hub

如果您在會議室中擁有一Microsoft Teams 會議室裝置或 Surface Hub，您可以設定協調會議。 協調會議可讓您設定 Teams 會議室 裝置和 Surface Hub，這樣當您在一個裝置上加入會議時，會議室中的其他裝置也會加入同一個會議。 您可以設定攝影機、喇叭和麥克風，讓參與者能夠獲得最佳體驗，而其他人則停用。 這可避免參與者在將多個裝置新加入會議時，可能遇到令人驚驚的回音和意見回應雜訊。

若要設定協調會議，您必須確定您的Teams 會議室裝置和 Surface Hub 已正確設定為參與會議。 最重要的是，每個裝置必須擁有自己的會議室Exchange信箱。 若要瞭解如何設定，請參閱下列文章：

- [部署 Microsoft Teams 會議室](../rooms/rooms-deploy.md)
- [建立 Surface Hub 2S 裝置帳戶](/surface-hub/surface-hub-2s-account)

確認您的裝置和 Surface Hub Teams 會議室自動接受會議並成功加入會議之後，您可以設定協調會議。

每個會議室應分別完成下列步驟。

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>步驟 1：規劃您的協調會議體驗

進行任何組組變更之前，您必須決定哪些裝置會在每個會議室中執行什麼操作。 也就是說，對於一個給定的會議室，您必須決定哪個裝置會擁有使用中麥克風、相機和白板。 您設定裝置的方式取決於您的特定環境，但以下是一些一般建議，請從以下開始著手：

- **麥克風** Teams 會議室裝置
- **相機** Teams 會議室預設 (開啟) Surface Hub (預設為關閉，但參與者可開啟) 
- **白板Surface Hub**

> [!IMPORTANT]
> 請確定只在一部裝置上啟用麥克風。 如果您在一部以上裝置上啟用，就會聽到音訊回音和意見回應。

## <a name="step-2-get-your-devices-upns"></a>步驟 2：取得您裝置 UPNs

當您在會議室中設定協調會議體驗時，您必須告知Teams 會議室裝置和 Surface Hubs 哪些裝置要協調。 這是在 UPN 中新增使用者主體名稱 (UPN) 其應協調的裝置之一。 如果您不知道要設定為協調會議之每個裝置使用的 UPNs，您可以使用 Microsoft 365 系統管理中心。 

您必須指派系統管理員角色才能存取Microsoft 365 系統管理中心。 詳細資訊，請參閱 [關於系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)。

若要取得您裝置Teams 會議室 Surface Hub 的 UPNs，請執行下列操作：

1. 請流覽 來Microsoft 365 系統管理中心帳戶 https://admin.microsoft.com 。
2. 前往 **UsersActive**  >  **使用者**。
3. 在顯示名稱欄中Teams 會議室裝置或Surface Hub名稱 (如果您有許多使用者，您可以使用搜尋) 。****
4. 在使用者名稱欄中尋找 UPN (其外觀會類似 alias@contoso.com 或 alias@contoso.onmicrosoft.com) 。****
5. 針對將參與協調會議的每個裝置重複此步驟。

## <a name="step-3-create-a-deployment-worksheet"></a>步驟 3：建立部署工作表

規劃協調會議體驗並收集裝置 UPNs 清單之後，建議建立部署工作表。 部署工作表可協助您將您想要設定的所有裝置設定視覺化，讓您驗證您的選擇並檢查錯誤。

在試算表應用程式中，新增第一欄中下列各欄的列：

| 設定                | 描述      |
|------------------------|-----------------|
| **音訊預設值**      | 決定會議開始時，麥克風會位於哪個裝置上。 只有一 (裝置Teams 會議室裝置) `true` `false` 可以設定此欄位，而其他裝置必須設定此欄位以避免音訊回音和意見回應。          |
| **音訊已啟用**      | 決定會議參與者是否可以開啟或關閉麥克風。 設定為 **音訊** `false` `false` 預設值的裝置應設定此設定，讓參與者不會不小心開啟麥克風，並造成音訊回音或意見回應。<p>如果 **音訊預設值** 設為 `true` ，此設定會被忽略，參與者可以將麥克風設為靜音或取消靜音。          |
| **視音訊預設值**      | 決定會議開始時相機會使用哪個裝置。 為了獲得最佳體驗，我們建議您只將Teams 會議室設定 `true` 為 ，而所有其他裝置都設為 `false` 。          |
| **啟用視像**      | 決定會議參與者是否可以開啟或關閉相機。 您可以在活動 `true` 參與者想要共用不同視 (，例如參與者使用 Surface Hub 白板) 。 如果您不希望參與者在裝置上開啟或關閉相機，請將其設定為 `false` 。<p> 如果 **視音訊預設值** 設定為 `true` ，此設定會被忽略，參與者可以開啟或關閉相機。         |
| **白板預設值** | 決定Teams 會議室裝置是否會顯示其中一個會議參與者共用的白板。 如果您擁有一個Surface Hub `false` `true` ，如果您還沒有，建議您將這個設定設定為。 此設定對 Surface Hub 沒有影響。 Surface Hubs 一定會顯示會議參與者共用的白板。         |
| **已啟用 Whiteboard** | 決定會議參與者是否可以開啟或關閉白板。 如果您不希望參與者在裝置上開啟或關閉白板，請將其設定為 `false` 。 <p>如果 **Whiteboard 預設** 設定為 `true` ，此設定會被忽略，參與者可以開啟或關閉白板。
| **信任的帳戶**   | 這是每個 Teams 會議室裝置或 Surface Hub 裝置應接受會議加入邀請，或應寄到哪些會議加入邀請的 UPN 逗號分隔清單。 |

在後續的欄，新增每個Teams 會議室裝置和 Surface Hub。 在每一欄中，填寫對應到您想要的會議室體驗的值。 以下是一個裝置和一個Teams 會議室 Surface Hub範例：

- Teams裝置
  - 會議開始時 **，音訊和** 視音訊會開啟。 參與者 **可以** 開啟或關閉音訊和視音訊。
  - 顯示共用白板已關閉。
- Surface Hub
  - 會議開始時 **，音訊** 會關閉。 參與者 **無法開啟** 或關閉音訊。
  - 會議開始時 **，視** 音訊會關閉。 參與者 **可以** 開啟或關閉視像。

| 設定                | Teams會議室      | Surface Hub      |
|------------------------|-----------------|------------------|
| **音訊預設值**      | `true`          | `false`          |
| **音訊已啟用**      | `true`          | `false`          |
| **視音訊預設值**      | `true`          | `false`          |
| **啟用視像**      | `true`          | `true`           |
| **白板預設值** | `false`         | `false`          |
| **信任的帳戶**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>步驟 4：設定Teams 會議室裝置

您可以使用裝置觸控式螢幕在 Teams 會議室 裝置上設定協調會議，或者，如果您需要設定許多裝置，而且想要從中央位置設定，您可以使用 XML 設定檔。

使用上一個步驟中建立工作表，協助您設定裝置。

### <a name="use-the-teams-rooms-devices-touch-screen"></a>使用Teams 會議室的觸控式螢幕

若要在裝置上設定協調會議，請執行下列操作：

1. 選取 **...更多**  >  **設定**。
2. 輸入系統管理員密碼，然後選取 **是**。
3. 選取 **協調會議**。
4. 在 **選項下**，將 **協調會議設定**_為 On_。
5. 如果 **工作表中的** 音訊預設為 `true` ，請設定開啟此裝置上的 **麥克風** ，否則請將其 _關閉_。
6. 如果 **工作表中** 已啟用音訊 `true` ，請選取在開啟此裝置麥克風下加入會議時允許 **人員啟用**。 如果開啟此裝置麥克風設為開啟，則無法關閉此選項。
7. 如果 **工作表中的影片** 預設為 ， `true` 請設定開啟此裝置相機，否則請將其 _關閉_。
8. 如果 **工作表中** 已啟用 `true` 視像，請選取在開啟此裝置相機下，讓人員加入會議 **時啟用**。 如果開啟此裝置相機的設定為開啟，則無法關閉 _此選項_。
9. 如果 **工作表中的 Whiteboard** 預設為 `true` ，請設定開啟此裝置上的白板，否則請將其 _關閉_。
10. 在 **信任的裝置帳戶下**，輸入工作表中列出 **之信任帳戶** 的每個 UPN。 使用逗號分隔多個 UPNs。
11. 選取 **儲存並離開**。

選取儲存 **並離開之後**，裝置會重新開機，並準備好參與協調會議。

### <a name="use-the-teams-rooms-xml-configuration-file"></a>使用 Teams 會議室 XML 設定檔

您可以使用裝置 XML 組Teams 會議室來設定 `SkypeSettings.xml` 協調會議。 檔案 `SkypeSettings.xml` 不是靜態檔案。 當Teams 會議室啟動時，它會檢查 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 名為 的檔案 `SkypeSettings.xml` 。 如果檔案存在，裝置會讀取並適用檔案中指定的組組。 完成安裝之後，檔案即會被刪除。 有關檔案詳細資訊， `SkypeSettings.xml` 請參閱使用 XML 設定檔 [管理主控台設定](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。

以下是設定檔中協調會議設定語法：

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false" enabled="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

若要在裝置上設定協調會議，請執行下列操作：

1. 在文字檔編輯器中 ，Visual Studio Code或記事本，將上述 XML 貼到新檔案中。

2. 將每個 XML 元素設定為試算表中的對應 `true` 或 `false` 值。 例如，如果 **音訊預設值** 為 `true` ，則設定 `<Audio default="true">` 。

3. 請務必變更為 `TrustedAccounts` UPNs 清單。

4. 使用名稱儲存檔案 `SkypeSettings.xml` 。

5. 將檔案放在Teams 會議室資料夾中 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。 您可以用幾種方法執行此工作：

    - **將檔案複製到您的** Teams 會議室您必須啟用檔案共用並建立網路共用，才能將檔案複製到您的裝置。 完成之後，您可以連接到網路共用，然後將檔案複製到裝置。 有關詳細資訊，請參閱[Microsoft Teams 會議室及作業](../rooms/rooms-operations.md)。
    - **使用群組原則** 建立群組原則以將檔案複製到裝置。 詳細資訊，請參閱 [群組原則概觀](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))。
    - **在裝置上** 下載Teams 會議室您可以使用系統管理模式登入裝置，然後將檔案從網路共用或 USB 磁碟機複製到裝置。 詳細資訊，請參閱 [切換到系統管理模式](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)。
    
6. 重新開機裝置。 您可以用幾種方法執行此工作：

    - **遠端 PowerShell** 您可以使用遠端 PowerShell 在裝置上執行關閉命令。 詳細資訊，請參閱 [使用 PowerShell 進行遠端系統管理](../rooms/rooms-operations.md)。
    - **執行重新開機電腦** 您可以在您的本地 `Restart-Computer` 電腦上執行 Cmdlet，並指定要重新開機之裝置的電腦名稱稱。 詳細資訊，請參閱 [重新開機電腦](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)。

## <a name="step-5-configure-surface-hub"></a>步驟 5：設定Surface Hub

您可以使用組Windows設計工具建立一個設定套件，您可以使用該套件將協調會議設定套用至 Surface Hub。 您將上述所建立之 XML 檔案貼到Windows設計工具中，以建立資源配置套件。

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>建立協調會議 XML 組Surface Hub

系統Windows設計工具Microsoft Intune，將協調會議組適用于您的 Surface Hub。 此組組是使用 XML 定義。 在進一步進行之前，您需要建立要申請的 XML。

以下是協調會議 XML 設定檔的語法。

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

請執行下列操作，準備 XML Windows設計工具或Microsoft Intune：

1. 在文字檔編輯器中 ，Visual Studio Code或記事本，將上述 XML 貼到新檔案中。

2. 將每個 XML 元素設定為試算表中的對應 `true` 或 `false` 值。 例如，如果 **音訊預設值** 為 `true` ，則設定 `<Audio default="true">` 。

3. 請務必變更為 `TrustedAccounts` UPNs 清單。

4. Windows設計工具，XML 必須位於單一行。 移除每一行之間的所有分行符號，讓 XML 看起來像這樣：

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. 將檔案儲存在電腦上。

建立 XML 組設定檔之後，請使用管理 Microsoft Teams 上的Surface Hub[設定](surface-hub-manage-config.md)，以將檔案Surface Hub Surface Hubs。