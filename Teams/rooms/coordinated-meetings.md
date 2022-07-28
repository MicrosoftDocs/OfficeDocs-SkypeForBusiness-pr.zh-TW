---
title: 使用 Microsoft Teams 會議室 和 Surface Hub 設定協調會議
ms.author: dstrome
author: dstrome
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
description: 設定Teams 會議室裝置和 Surface Hub 在一部或另一部裝置加入會議時加入會議。
ms.openlocfilehash: 1f249e9bd0321c9e8afd984aca90f902ad80d444
ms.sourcegitcommit: 644374fcad6372494e87d729de690af4c060f635
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2022
ms.locfileid: "67054934"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>使用 Microsoft Teams 會議室 和 Surface Hub 設定協調會議

如果您在會議室中有一或多個Microsoft Teams 會議室裝置或 Surface Hub，您可以設定「協調會議」。 [協調會議] 可讓您設定Teams 會議室裝置和 Surface Hub，這樣當您在一個裝置上加入會議時，會議室中的其他裝置也會加入同一個會議。 您可以設定相機、喇叭和麥克風，讓參與者獲得最佳體驗，同時停用其他人。 這可避免在將多個裝置新增到會議時，遇到無法讀取的回音和意見反應噪音參與者。

若要設定「協調會議」，您必須確定您的Teams 會議室裝置和 Surface Hub 已正確設定為參與會議。 最重要的是，每個裝置都必須有自己的 Exchange 會議室信箱。 如需如何設定它們的相關資訊，請參閱下列文章：

- [部署 Microsoft Teams 會議室](../rooms/rooms-deploy.md)
- [建立 Surface Hub 2S 裝置帳戶](/surface-hub/surface-hub-2s-account)

確認您的Teams 會議室裝置和 Surface Hub 可以自動接受會議並成功加入會議之後，您可以設定「協調會議」。

下列步驟應分別針對每個會議室完成。

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>步驟 1：規劃您的協調會議體驗

進行任何設定變更之前，您必須決定哪些裝置會在每一個會議室中執行什麼動作。 也就是說，對於指定的會議室，您必須決定哪個裝置將具有使用中的麥克風、相機和白板。 您設定裝置的方式取決於您的特定環境，但以下是一些一般建議的開頭：

- **麥克風** Teams 會議室裝置
- **相機** Teams 會議室裝置預設 () 開啟，而 Surface Hub 預設會 (關閉，但參與者允許) 
- **白板** Surface Hub

> [!IMPORTANT]
> 請確定您只在一部裝置上啟用麥克風。 如果您在多個裝置上啟用此功能，您將會體驗音訊回音和意見反應。

## <a name="step-2-get-your-devices-upns"></a>步驟 2：取得裝置的 UPN

當您在會議室中設定「協調會議」體驗時，您需要告知會議室中Teams 會議室裝置和 Surface Hub 要與哪些裝置協調。 這是透過將使用者主體名稱新增 (UPN) 應該與其設定協調的裝置來完成。 如果您不知道要針對協調會議設定的每一個裝置的 UPN，您可以使用Microsoft 365 系統管理中心找到它們。 

您必須獲派系統管理員角色才能存取Microsoft 365 系統管理中心。 如需詳細資訊，請參閱 [關於系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)。

若要取得 Teams 會議室 裝置和 Surface Hub 的 UPN，請執行下列動作：

1. 流覽以登入Microsoft 365 系統管理中心 https://admin.microsoft.com 。
2. 移至 **[使用者**  >  **作用中使用者]**。
3. 在 [**顯示名稱**] 欄中尋找Teams 會議室裝置或 Surface Hub 的名稱 (如果您有許多使用者) ，您可以使用 **[搜尋**] 方塊。
4. 在 [ **使用者名稱** ] 欄中尋找 UPN (它看起來會像是 alias@contoso.com 或 alias@contoso.onmicrosoft.com) 。
5. 針對參與協調會議的每個裝置重複此步驟。

## <a name="step-3-create-a-deployment-worksheet"></a>步驟 3：建立部署工作表

在您規劃協調會議體驗並收集裝置 UPN 清單之後，建議您建立部署工作表。 部署工作表可協助您視覺化您要在所有裝置上設定的設定，讓您驗證選項並檢查錯誤。

在試算表應用程式中，在第一欄中新增下列列：

| 設定                | 描述      |
|------------------------|-----------------|
| **音訊預設值**      | 決定當會議開始時，麥克風會在哪個裝置上作用中。 通常只有一個裝置 (Teams 會議室裝置) 可以將此欄位設定為 `true` ，而其他裝置必須設定此欄位，以避免 `false` 音訊回音和意見反應。          |
| **已啟用音訊**      | 判斷會議中的參與者是否可以開啟或關閉麥克風。 設為 `false` **Audio 預設** 值的裝置應將此設定設為 `false` ，讓參與者無法意外開啟麥克風並造成音訊回音或意見反應。<p>如果 **音訊預設** 值設為 `true` ，此設定會被忽略，參與者可以將麥克風設為靜音或取消靜音。          |
| **視訊預設值**      | 決定會議開始時相機會在哪個裝置上使用。 為獲得最佳體驗，建議您在所有其他裝置都設 `false` 為 `true` 時，只設定Teams 會議室裝置。          |
| **已啟用視訊**      | 判斷會議中的參與者是否可以開啟或關閉相機。 您可以將此設定在 `true` 活動參與者想要分享不同視訊觀點的任何其他裝置上， (例如參與者正在使用 Surface Hub 白板) 。 如果您不希望參與者在裝置上開啟或關閉相機，請將此設定設為 `false` 。<p> 如果 **[視訊] 預設** 值設為 `true` ，則會忽略此設定，且參與者可以開啟或關閉相機。         |
| **Whiteboard 預設值** | 判斷Teams 會議室裝置是否會顯示由其中一個會議參與者共用的白板。 如果您有 Surface Hub 且沒有 Surface Hub `true` ，建議您設定此 `false` 設定。 此設定對 Surface Hub 沒有作用。 Surface Hubs 一律會顯示由會議參與者共用的白板。         |
| **已啟用白板** | 決定會議中的參與者是否可以開啟或關閉白板。 如果您不希望參與者在裝置上開啟或關閉白板，請將此設定設為 `false` 。 <p>如果 **Whiteboard 預設** 值設為 `true` ，則會忽略此設定，且參與者可以開啟或關閉白板。
| **信任的帳戶**   | 這是每個 Teams 會議室裝置或 Surface Hub 的逗號分隔 UPN 清單，裝置應接受會議加入邀請，或應傳送會議加入要求。 |

在後續的欄中，新增每個Teams 會議室裝置和 Surface Hub。 在每一欄中，填寫與您想要的會議室體驗相對應的值。 以下是一個Teams 會議室裝置和一個 Surface Hub 的範例：

- Teams 裝置
  - 會議 **開始時會** 開啟音訊和視訊。 參與者 **可以** 開啟或關閉音訊和視訊。
  - 顯示共用白板已關閉。
- Surface Hub
  - 會議開始時，音訊會 **關閉** 。 參與者 **無法** 開啟或關閉音訊。
  - 會議開始時會 **關閉** 視訊。 參與者 **可以** 開啟或關閉視訊。

| 設定                | Teams 會議室      | Surface Hub      |
|------------------------|-----------------|------------------|
| **音訊預設值**      | `true`          | `false`          |
| **已啟用音訊**      | `true`          | `false`          |
| **視訊預設值**      | `true`          | `false`          |
| **已啟用視訊**      | `true`          | `true`           |
| **Whiteboard 預設值** | `false`         | `false`          |
| **信任的帳戶**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>步驟 4：設定Teams 會議室裝置

您可以使用裝置的觸控螢幕，在Teams 會議室裝置上設定「協調會議」，或者，如果您需要設定許多裝置，而且想要從中央位置設定，則可以使用 XML 組態檔。

使用您在上一個步驟中建立的工作表來協助您設定裝置。

### <a name="use-the-teams-rooms-devices-touch-screen"></a>使用Teams 會議室裝置的觸控螢幕

若要在裝置上設定協調會議，請執行下列動作：

1. 選取 **...[其他**  >  **設定]**。
2. 輸入系統管理員密碼，然後選取 **[是]**。
3. 選取 **[協調會議]**。
4. 在 [ **選項] 底** 下，將 [ **協調會議** ] 設為 _[開啟]_。
5. 如果工作表中的 **音訊預設** 值是 `true` ，請將 **[開啟此裝置的麥克風** ] 設為開啟，否則保持 _關閉_。
6. 如果工作表 `true` 中 **已啟用音訊**，請選取 [**開啟此裝置的麥克風**] 底下的 [**讓人員加入會議時啟** 用]。 如果 [ **開啟此裝置的麥克風** ] 設定為 [開啟]，就無法關閉此選項。
7. 如果工作表中的 **[視訊] 預設** 值為 `true` ，請將 **此裝置的相機** 設為開啟，否則 _保持關閉_。
8. 如果工作表中 **已啟用** 視訊 `true` ，請在 [**開啟此裝置的相機**] 底下，選取 [**讓人員加入會議時啟** 用]。 如果將 [ **開啟此裝置的相機** ] _設為 [_ 開啟]，就無法關閉此選項。
9. 如果工作表中的 **Whiteboard 預設** 值為 `true` ，請將 **此裝置上的白板** 設定為 _開_ 啟，否則 _保持關閉_。
10. 在 **[信任的裝置帳戶**] 底下，輸入工作表中 [ **信任的帳戶** ] 中所列的每個 UPN。 使用逗號分隔多個 UPN。
11. 在信任的裝置上，關閉遠端鄰近和會議室。 
12. 選 **取 [儲存並結束]**。

選取 [ **儲存並結束**] 之後，裝置將會重新開機，並準備好參與協調會議。

### <a name="use-the-teams-rooms-xml-configuration-file"></a>使用 Teams 會議室 XML 組態檔

您可以使用Teams 會議室裝置的 XML 組態檔來設定協調會議 `SkypeSettings.xml` 。 檔案 `SkypeSettings.xml` 不是靜態檔案。 當Teams 會議室裝置啟動時，它會存回 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 名為 `SkypeSettings.xml` . 的檔案。 如果檔案存在，裝置會讀取並套用檔案中指定的設定。 套用設定完成後，檔案就會刪除。 如需有關檔案的 `SkypeSettings.xml` 詳細資訊，請參閱 [使用 XML 組態檔管理主機設定](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。

以下是組態檔中 [協調會議] 設定的語法：

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

若要在裝置上設定協調會議，請執行下列動作：

1. 在文字檔編輯器中，例如Visual Studio Code或記事本，將上述的 XML 貼到新檔案中。

2. 將每個 XML 元素設定為試算表中的對應 `true` 或 `false` 值。 例如，如果 **Audio 預設** 值為 `true` ，則設定 `<Audio default="true">` 。

3. 請務必變更 `TrustedAccounts` 為 UPN 清單。

4. 以名稱儲存檔案 `SkypeSettings.xml` 。

5. 將檔案放在Teams 會議室裝置 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 的資料夾中。 您可以透過下列幾種方式執行此動作：

    - **將檔案複製到Teams 會議室裝置** 您必須啟用檔案共用並建立網路共用，才能將檔案複製到您的裝置。 完成之後，您可以連線到網路共用，並將檔案複製到裝置。 如需詳細資訊，請[參閱Microsoft Teams 會議室維護與作業。](../rooms/rooms-operations.md)
    - **使用群組原則** 建立群組原則以將檔案複製到裝置。 如需詳細資訊，[請參閱群組原則概觀]](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))。
    - 在 **Teams 會議室裝置上下載檔案** 您可以使用管理員模式登入裝置，然後從網路共用或 USB 磁片磁碟機將檔案複製到裝置。 如需詳細資訊，請參閱[切換至管理員模式](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)。
    
6. 重新開機裝置。 您可以透過下列幾種方法執行此動作：

    - **遠端 PowerShell** 您可以使用遠端 PowerShell 在裝置上執行關機命令。 如需詳細資訊，請參閱 [使用 PowerShell 遠端系統管理](../rooms/rooms-operations.md)。
    - **執行 Restart-Computer** 您可以在本機電腦上執行 `Restart-Computer` Cmdlet，並指定您要重新開機之裝置的電腦名稱稱。 如需詳細資訊，請參閱 [重新開機電腦](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)。

## <a name="step-5-configure-surface-hub"></a>步驟 5：設定 Surface Hub

您可以使用 Windows 設定設計工具來建立布建套件，以便將 [協調會議] 設定套用至 Surface Hub。 您將將上述建立的 XML 檔案貼到 Windows 設定設計工具中，以建立布建套件。

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>為 Surface Hub 建立協調會議 XML 組態檔

Windows 設定設計工具和Microsoft Intune都可用來將協調會議設定套用到您的 Surface Hub。 設定是使用 XML 定義的。 在您更進一步之前，您必須建立將會套用的 XML。

以下是「協調會議 XML」組態檔的語法。

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

請執行下列操作以準備適用于 Windows 設定設計工具或 Microsoft Intune 的 XML：

1. 在文字檔編輯器中，例如Visual Studio Code或記事本，將上述的 XML 貼到新檔案中。

2. 將每個 XML 元素設定為試算表中的對應 `true` 或 `false` 值。 例如，如果 **Audio 預設** 值為 `true` ，則設定 `<Audio default="true">` 。

3. 請務必變更 `TrustedAccounts` 為 UPN 清單。

4. Windows 設定設計工具需要將 XML 放在單一行上。 移除每一行之間的所有分行符號，讓 XML 看起來像這樣：

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. 將檔案儲存在電腦上。

建立 XML 組態檔之後，請使用在 [Surface Hub 上管理 Microsoft Teams 設定](surface-hub-manage-config.md) 中的步驟，將它套用到 Surface Hub。
