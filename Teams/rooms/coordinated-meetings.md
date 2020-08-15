---
title: 使用 Microsoft 團隊聊天室和 Surface Hub 來設定協同會議
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
localization_priority: Normal
description: 在一部裝置或其他人加入會議時，設定團隊室裝置和 Surface Hub 加入會議。
ms.openlocfilehash: c1200b4e949cb866440907f8577f61f4528630e2
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761431"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>使用 Microsoft 團隊聊天室和 Surface Hub 來設定協同會議

如果您在會議室中有一個或多個 Microsoft 團隊聊天室裝置或 Surface Hub，您可以設定協同會議。 [協調式會議] 可讓您設定小組室裝置和 Surface Hub，這樣當您在一部裝置上加入會議時，會議室中的其他裝置也會加入相同的會議。 您可以設定相機、喇叭和麥克風，讓參與者能在其他人停用時啟用最佳體驗。 如此一來，就能避免令人可怕的回音與意見反應，在新增多個裝置到會議時，可能會遇到

若要設定協同會議，您必須確認您的小組室裝置和 Surface Hub 已正確設定為參與會議。 最重要的是，每個裝置都需要有自己的 Exchange 會議室信箱。 如需如何設定的詳細資訊，請參閱下列文章：

- [部署 Microsoft Teams 會議室](../rooms/rooms-deploy.md)
- [建立 Surface Hub 2 的裝置帳戶](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

確認您的小組機房裝置和 Surface Hub 可以自動接受會議並成功加入會議之後，您就可以設定協同會議。

必須針對每個會議室單獨完成下列步驟。 一個會議室中的裝置不應設定為與其他會議室中的裝置進行協調的會議。

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>步驟1：規劃您的協同會議體驗

變更任何設定前，您必須決定哪些裝置將會在每個會議室中執行哪些動作。 亦即，對於指定的會議室，您必須決定要使用 [作用中麥克風]、[相機] 和 [白板] 的裝置。 您設定裝置的方式取決於您的特定環境，以下是開始使用的一些一般建議：

- **麥克風** 團隊聊天室裝置
- **相機** 團隊會議室裝置預設會 () 和 Surface Hub (預設為關閉，但允許) 參與者開啟
- **白板** Surface Hub

> [!IMPORTANT]
> 請確定您只在一個裝置上啟用麥克風。 如果您在多個裝置上啟用，您會遇到音訊回音和意見反應。

## <a name="step-2-get-your-devices-upns"></a>步驟2：取得您的裝置 Upn

當您在會議室中設定共同會議體驗時，您必須將小組室裝置和 Surface Hub 告知在該房間中要與之共同合作的裝置。 如此一來，您可以將使用者主體名稱 (UPN) 與其設定共同合作的裝置。 如果您不知道您想要為其設定協同會議的每個裝置的 Upn，您可以使用 Microsoft 365 系統管理中心來找到它們。 

您必須獲指派系統管理員角色，才能存取 Microsoft 365 系統管理中心。 如需詳細資訊，請參閱 [關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

若要取得團隊聊天室裝置和 Surface Hub 的 Upn，請執行下列動作：

1. 透過造訪登入 Microsoft 365 管理中心 https://admin.microsoft.com
2. 移至 [**使用者**作用中的  >  **使用者**]
3. 在 [ **顯示名稱** ] 欄中尋找您團隊聊天室裝置或 Surface Hub 的名稱 (如果您有多個使用者) ，您就可以使用 [ **搜尋** ] 方塊。
4. 在 [使用者 **名稱** ] 欄中尋找 UPN (它看起來像是 alias@contoso.com 或 alias@contoso.onmicrosoft.com) 
5. 針對將參與協同會議的每個裝置重複此步驟

## <a name="step-3-create-a-deployment-worksheet"></a>步驟3：建立部署工作表

在您規劃了您的協調會議體驗並收集您的裝置 Upn 清單後，最好先建立部署工作表。 部署工作表可協助您視覺化您想要在所有裝置上設定的設定，讓您驗證選項並檢查錯誤。

在試算表應用程式中，在第一欄中新增下列各列：

| 設定                | 描述      |
|------------------------|-----------------|
| **音訊預設值**      | 決定會議開始時麥克風起作用的裝置。 只有一個裝置 (通常是團隊會議室裝置) 可以將此欄位設定為， `true` 而其他裝置必須將此欄位設定為， `false` 以避免音訊回顯和意見反應。          |
| **已啟用音訊**      | 決定會議中的參與者是否可以開啟或關閉麥克風。 在其上設定 **音訊預設值** 的裝置， `false` 應該將此設定設定為， `false` 讓參與者不會不小心開啟麥克風並導致音訊回音或意見反應。<p>如果 [ **音訊預設值** ] 設定為 `true` ，則會忽略此設定，且參與者可以將麥克風設為靜音或取消靜音。          |
| **影片預設值**      | 決定會議開始時，相機在哪一個裝置上起作用。 為了獲得最佳體驗，我們建議您只有在 `true` 所有其他裝置都設定為時，才會將小組聊天室裝置設定為 `false` 。          |
| **已啟用影片**      | 決定會議中的參與者是否可以開啟或關閉相機。 您可以 `true` 在活動參與者中的任何其他裝置上將此設定為 [共用]， (例如參與者使用 Surface Hub 白板) 。 如果您不希望參與者在裝置上開啟或關閉相機，請將此選項設定為 `false` 。<p> 如果 [ **影片預設值** ] 設定為 `true` ，則會忽略此設定，且參與者可以開啟或關閉相機。         |
| **白板預設值** | 判斷小組聊天室裝置是否會顯示由其中一個會議參與者共用的白板。 我們建議您將它設定為 `false` 如果您有 Surface Hub，且您沒有它 `true` 。 此設定不會影響 Surface Hub。 Surface Hub 將永遠顯示由會議參與者共用的白板。         |
| **信任帳戶**   | 這是一個以逗號分隔的 Upn 清單，其中包含裝置應接受會議加入要求的每個小組房間裝置或 Surface Hub，或應傳送給哪個會議連接要求。 |

在後續的欄中，新增每個小組房間裝置和 Surface Hub。 在每一欄中，填入與您想要的會議室相符的值。 以下是一個團隊聊天室裝置和一個 Surface Hub 的範例：

- 團隊裝置
  - **在會議開始時，** 音訊和影片都會開啟。 參與者 **可以** 開啟或關閉音訊與影片。
  - 顯示共用的白板功能已關閉。
- Surface Hub
  - 音訊會在會議開始時 **關閉** 。 參與者 **無法** 開啟或關閉音訊。
  - 影片會在會議開始時 **關閉** 。 參與者 **可以** 開啟或關閉影片。

| 設定                | 團隊聊天室      | Surface Hub      |
|------------------------|-----------------|------------------|
| **音訊預設值**      | `true`          | `false`          |
| **已啟用音訊**      | `true`          | `false`          |
| **影片預設值**      | `true`          | `false`          |
| **已啟用影片**      | `true`          | `true`           |
| **白板預設值** | `false`         | 不適用   |
| **信任帳戶**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>步驟4：設定團隊聊天室裝置

您可以使用裝置的觸控式螢幕在團隊聊天室裝置上設定共同作業，或者，如果您需要設定多個裝置，並想要從中央位置執行此操作，您可以使用 XML 設定檔。

使用您在上一個步驟中建立的工作表，協助您設定裝置。

### <a name="use-the-teams-rooms-devices-touch-screen"></a>使用團隊聊天室裝置的觸控式螢幕

若要在裝置上設定協同會議，請執行下列動作：

1. 選取 **.。。其他**  >  **設定**
2. 輸入系統管理員密碼，然後選取 **[是]**
3. 選取 [**協調的會議**]
4. 將 [ **選項**] 底下的 [ **協調會議** ] 設定為 [開啟]
5. 如果您工作表中的 [ **音訊預設值** ] 是 `true` ，請將 **此裝置的麥克風** 設定為 [開啟]，否則請將其關閉
6. 如果您的工作表中**啟用音訊** `true` ，請選取 [**開啟此裝置的麥克風**] 下的 [**讓人員在加入會議時啟用**]。 如果將 **此裝置的麥克風** 設為 [開啟]，則無法關閉此選項。
7. 如果您工作表中的 [ **影片預設值** ] 是 `true` ，請將 **此裝置的相機** 設定為 [開啟]，否則請將其關閉
8. 如果您的工作表中啟用了 [**影片**] `true` ，請選取 [**開啟此裝置的相機**] 底下的 [**讓人員在加入會議時啟用**]。 如果將 **此裝置的相機** 設為 [開啟]，則無法關閉此選項。
9. 如果工作表中的 **白板預設值** 是 `true` ，請將 [ **開啟此裝置上的 whiteboarding** ] 設為 [開啟]，否則請將其關閉
10. 在 [ **受信任的裝置帳戶**] 底下，于工作表的 [ **信任帳戶** ] 中，輸入每個 UPN。 使用逗號分隔多個 Upn。
11. 選取 [**儲存並退出**]

在您選取 [ **儲存並**結束] 之後，裝置將會重新開機，並準備好參與協同會議。

### <a name="use-the-teams-rooms-xml-configuration-file"></a>使用團隊聊天室 XML 設定檔

您可以使用團隊聊天室裝置的 XML 設定檔來設定協同會議 `SkypeSettings.xml` 。 檔案 `SkypeSettings.xml` 不是靜態檔案。 小組聊天室裝置啟動時，會將檔案檢入至 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 名為的檔案 `SkypeSettings.xml` 。 如果檔案存在，裝置會讀取並套用檔案中指定的配置。 完成設定之後，就會刪除檔案。 如需檔案的詳細資訊 `SkypeSettings.xml` ，請參閱 [使用 XML 設定檔管理主控台設定](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。

以下是設定檔中 [協調會議] 設定的語法：

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

若要在裝置上設定協同會議，請執行下列動作：

1. 在文字檔編輯器（例如 Visual Studio 程式碼或記事本）中，將上述 XML 貼到新檔案中
2. 將每個 XML 元素設定為 `true` `false` 試算表中對應的 or 值。 例如，如果 **音訊預設值** 為 `true` ，請設定 `<Audio default="true">` 。
3. 請務必變更 `TrustedAccounts` 為您的 upn 清單
4. 以名稱儲存檔案 `SkypeSettings.xml`
5. 將檔案放在團隊聊天室裝置的 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 資料夾中。 您可以使用下列幾種方法來執行此動作：
    - **將檔案複製到您的小組聊天室裝置** 您必須先啟用檔案共用並建立網路共用，才能將檔案複製到您的裝置。 完成之後，您就可以連線到網路共用，並將檔案複製到裝置上。 如需詳細資訊，請參閱 [Microsoft 團隊會議室維護與作業](../rooms/rooms-operations.md)。
    - **使用群組原則** 建立將檔案複製到裝置的群組原則。 如需詳細資訊，請參閱 [群組原則概述](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))。
    - **在團隊聊天室裝置上下載** 檔案您可以使用系統管理模式登入裝置，然後從網路共用或 USB 磁片磁碟機將檔案複製到裝置。 如需詳細資訊，請參閱 [切換到 [管理員模式]](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)。
6. 重新開機裝置。 您可以透過幾種方式來執行此動作：
    - **遠端 PowerShell** 您可以在使用遠端 PowerShell 的裝置上執行 [關閉] 命令。 如需詳細資訊，請參閱 [使用 PowerShell 進行遠端系統管理](../rooms/rooms-operations.md)。
    - **執行重新開機-電腦** 您可以 `Restart-Computer` 在本機電腦上執行 Cmdlet，並指定您想要重新開機之裝置的電腦名稱稱。 如需詳細資訊，請參閱 [重新開機電腦](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)。

## <a name="step-5-configure-surface-hub"></a>步驟5：設定 Surface Hub

您可以使用 Windows 配置設計工具來建立預配套件，您可以用來將 [協調會議] 設定套用到 Surface Hub。 您會將您在上面建立的 XML 檔案貼到 Windows 配置設計工具中，以建立預配套件。

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>建立 Surface Hub 的協調會議 XML 設定檔

Windows 配置設計工具和 Microsoft Intune 都是用來將 [協調會議] 設定套用到 Surface Hub。 此設定是使用 XML 定義的。 在您繼續進行之前，您必須先建立要套用的 XML。

以下是協同會議 XML 設定檔的語法。

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

請執行下列動作以準備 Windows 配置設計工具或 Microsoft Intune 版 XML：

1. 在文字檔編輯器（例如 Visual Studio 程式碼或記事本）中，將上述 XML 貼到新檔案中
2. 將每個 XML 元素設定為 `true` `false` 試算表中對應的 or 值。 例如，如果 **音訊預設值** 為 `true` ，請設定 `<Audio default="true">` 。
3. 請務必變更 `TrustedAccounts` 為您的 upn 清單
4. Windows 配置設計工具要求 XML 在單一行上。 移除各行之間的所有分行符號，使 XML 看起來像以下這樣：

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. 將檔案儲存在您的電腦上

建立 XML 設定檔之後，請使用「 [管理 Surface Hub 上的 Microsoft 團隊設定](surface-hub-manage-config.md) 」中的步驟，將其套用至 surface hub。