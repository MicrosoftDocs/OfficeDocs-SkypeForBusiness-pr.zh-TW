---
title: 如何使用 Microsoft Teams 面板裝置
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: 本文提供如何使用 Teams 面板裝置的指導方針。
ms.openlocfilehash: fff3df797e043b83662aacc9a67ef1af45b733a4
ms.sourcegitcommit: ab8f8e101e41774668b5e607fa72442105ca796e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2022
ms.locfileid: "68801774"
---
# <a name="how-to-use-microsoft-teams-panels"></a>如何使用 Microsoft Teams 面板

Microsoft Teams 面板是壓縮的數字顯示設備，安裝在會議空間外，通常位於進入旁邊。 這些觸控螢幕面板是專屬的 Microsoft Teams 裝置，可讓您快速檢視會議空間和排定的會議。 透過生動的色彩編碼 LED 和主畫面指示器，您可以判斷空間是否可供使用或從遠處保留。 您可以使用 Teams 面板，現場為臨時會議保留可用的會議空間。

Teams 面板裝置已預先安裝 Microsoft Teams，並顯示透過 Outlook 或 Teams 行事曆排程的會議詳細資料。

本文提供有關如何使用 Teams 面板裝置的指引給使用者和系統管理員。 它也會提供有關使用這些裝置的 [常見問題解答](#frequently-asked-questions) 。

如需面板裝置的概觀，以及如何在貴組織中規劃、交付及管理這些裝置的指導方針，請參閱 [部署 Microsoft Teams 面板](teams-panels.md)。

如需快速入門，請參閱 [開始使用 Teams 面板](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)。

## <a name="teams-panels-end-user-experience"></a>Teams 面板使用者體驗

探索 Teams 面板裝置的 [主畫面](#explore-teams-panels-home-screen) ，以檢視會議空間和會議詳細資料。 或者，點選並捲動觸控螢幕面板以執行其他動作。

使用您的 Teams 面板裝置來：

- [檢視會議空間詳細資料與可用性、會議詳細資料、預定預訂](#explore-teams-panels-home-screen)
- [保留可用的會議空間](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [回報問題](#report-a-problem)
- [檢視或更新裝置設定](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>探索 Teams 面板首頁畫面

主畫面是 Teams 面板裝置的主要視覺介面。  

您可以從主畫面檢視位置和會議詳細資料、預約空間、檢視即將到來的預約，以及識別目前的顯示狀態。

下列螢幕擷取畫面顯示 Teams 面板首頁畫面上的不同部分或磚：

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="此螢幕擷取畫面顯示 Teams 面板首頁畫面上的不同區域。":::

請參閱下表以瞭解每個磚的描述：

瓦 | 描述
:---|:---
**1-目前時間、日、日期和會議空間詳細資料** | 顯示目前的時間、日期、日期和會議空間名稱。 會議空間名稱是登入面板的資源帳戶名稱。
**兩個會議空間可用性和會議詳細資料** | 表示會議空間可用性，並顯示會議詳細資料。 請參閱 [會議空間可用性和會議詳細資料磚](#meeting-space-availability-and-meeting-details-tile)。
**3-Upcoming 行事曆** | 顯示會議空間行事曆和可用性，從目前這小時起最多 24 小時。 向上或向下捲動，以決定哪些時段可供使用，以及保留哪些時段。
**4-Settings** | 顯示 [ **設定]** 圖示。 點選它以回報問題或更新可用的裝置設定。

### <a name="meeting-space-availability-and-meeting-details-tile"></a>會議空間可用性和會議詳細資料磚

此磚的外觀及其功能會根據會議空間可用性和預約類型而有所不同。

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>會議空間是保留給已排程的會議

這個磚會以紫色的方式顯示在已透過 Outlook 或 Teams) 排程的已排程會議 (的會議空間中。 它會以顯眼的文字、會議開始和結束時間，以及會議召集人的名稱來顯示會議標題。 Teams 會議也會顯示 Teams 標誌。 會議詳細資料會醒目顯示，出席者可以輕鬆地確認他們位於正確的會議空間、適當的時間，以及正確的會議。

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams 面板首頁畫面顯示會議空間已保留給已排程的會議。":::

> [!NOTE]
>
> - 排程會議之後，最多可能需要 90 秒的時間，行事曆才會同步處理，並在面板螢幕上反映。
> - 針對 [標示為私人的已排程會議](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d)，會顯示 **私人會議** ，而非實際的會議標題。

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>為臨時會議保留會議空間

此磚會以紫色顯示，以供 [臨時會議所保留](#reserve-meeting-spaces-for-ad-hoc-meetings)的會議空間使用。 它會將 **會議** 開始和結束時間一併顯示在顯眼的文字中。 臨時會議會自動排程為 Teams 會議，因此 Teams 標誌一律會顯示在螢幕上。

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams 面板首頁畫面顯示會議空間已保留給臨時會議。":::

#### <a name="meeting-space-is-available"></a>會議空間可用

磚會在可用的會議空間中以綠色顯示。 它會 **顯示在** 顯眼的文字中可用，而且您也可以點選 [ **保留** ] 按鈕來 [保留臨時會議的會議空間](#reserve-meeting-spaces-for-ad-hoc-meetings)。 您可以) 右下方磚 (查看預定的會議空間行事曆，以決定臨時會議的結束時間。

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="此螢幕擷取畫面顯示當會議空間可用時，Teams 面板首頁畫面的顯示方式。":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>保留臨時會議的會議空間

您可以直接從臨時會議的面板中保留 [可用的會議空間](#meeting-space-is-available) 。 所有臨時會議都會自動排程為 Teams 會議。 不過，一旦保留之後，您就無法透過面板釋放或保留該會議空間。 只有裝置資源帳戶的系統管理員可以透過 Outlook 或 Teams 行事曆取消臨時會議 (，) 無法保留空間。

針對直接從面板預訂的臨時會議：

- 開始時間一律是目前的時間，因此您無法將它排程到未來的時間。
- 結束時間可以是到下一個排程的會議，或從目前這小時起最多 24 小時，以較早者為准。 查看 [首頁] 畫面上的 [ **預定行事曆** ] 磚，以判斷會議空間可供使用或預約的時段。

若要為臨時會議保留可用的會議空間：

1. 在主畫面上，點選 [ **保留]** 按鈕。
    :::image type="content" source="../media/panels-reserve.png" alt-text="顯示 [保留] 按鈕的 Teams 面板首頁畫面。":::
2. 在 **臨時會議** 畫面中，檢閱可用的結束時間選項。 您可以使用向右或向左鍵來流覽可用的結束時間選項。

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="顯示結束時段的臨時會議畫面。":::

    > [!Note]
    >
    > - 結束時間選項會以一小時的 15 分鐘間隔顯示。
    > - 結束時間預設為接下來的 15 分鐘間隔，至少會比目前時間後 5 分鐘。 例如，如果目前的時間是下午 1：57，預設的結束時間會顯示為下午 2：15，而不是下午 2：00。 這可防止使用者預約 5 分鐘或更少的空間。 在上述螢幕擷取畫面中，預設的結束時間會顯示為下午 2：00，也就是在目前時間 (下午 1：53) 後至少 5 分鐘的未來 15 分鐘間隔。
    > - 上述規則的例外狀況是，下一個會議的開始時間距離目前時間只有五分鐘內。 在這種情況下，您可以預約空間，直到下一個會議開始時間。 例如，如果目前時間是下午 1：57，而下一個會議的開始時間是下午 2：00，則下午 2：00 會顯示為唯一的結束時間選項，您可以保留空格三分鐘。

3. 點選所要的結束時間間隔，然後點選 [ **保留]**。

    確認視窗隨即出現，其中有豎起大拇指表情圖示、會議開始和結束時間，以及會議空間名稱。
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="臨時會議確認訊息。":::
[首頁] 畫面上的右磚現在會以紫色 **顯示，並** 顯示保留文字和 Teams 標誌。 這表示會議空間現在已保留給臨時 Teams 會議。
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="主畫面顯示臨時會議所保留的會議空間。":::

    > [!NOTE]
    > 如果會議空間是 Microsoft Teams 會議室，您可以使用會議室內的 Microsoft Teams 會議室或 Surface Hub 裝置 _加入_ 此 Teams 會議。

### <a name="report-a-problem"></a>回報問題

若要回報裝置或會議空間的問題、要求功能更新或提供任何意見反應，請使用主畫面上的 [ **設定** ] 圖示。

1. 點選主畫面上的 [ **設定]** 齒輪圖示。

2. 點選 [ **回報問題]** 選項。

    [ **傳送意見反應** ] 畫面會以表單格式顯示。
3. 從 [ **類型]** 下拉式清單中，選取要求類型。
4. 從 [ **問題]** 下拉式清單中，選取類別。
5. 在 [ **標題** ] 文字欄位中，使用面板鍵台輸入標題。
6. 如有需要，請在 **[標題**] 下方的文字欄位中輸入其他詳細資料。

    > [!NOTE]
    > 請勿包含任何可識別個人的資訊。

7. 檢閱您的專案，然後點 **選 [傳送]**。

### <a name="view-or-update-a-device-setting"></a>檢視或更新裝置設定

有幾個裝置設定，例如關於、協助工具、重新開機和隱私權原則，您可以直接從面板檢視或更新。 可用的裝置設定可能會根據裝置的原始設備製造商 (OEM) 而有所不同。 如需裝置特定設定的相關資訊，請參閱 OEM 檔。

若要檢視或更新裝置設定：

1. 點選主畫面上的 [ **設定]** 圖示。
2. 在 [ **設定] 畫面中** ，點選 **[裝置設定]**。
3. 在 [ **裝置設定]** 畫面中，點選您要檢視或更新的設定。
4. 依照畫面上的提示來檢視或更新設定。

## <a name="teams-panels-admin-experience"></a>Teams 面板系統管理員體驗

如果您是 [Teams 面板資源帳戶的](teams-panels.md\#resource-account-provisioning)系統管理員，那麼您也是裝置上 **面板應用程式** 的系統管理員。 身為 **面板 App** 系統管理員，除了管理裝置上的面板 **應用程式** 設定之外，您還可以執行 [使用者體驗](#teams-panels-end-user-experience)一節中提及的所有功能。

您的面板裝置提供兩種類型的系統管理設定。 您必須是裝置系統管理員，才能存取可用的系統管理員設定。 使用者無法存取這些設定。

- 管理員裝置特有的設定，例如顯示器、時間和日期、語言、藍牙、WiFi 等。 請參閱 OEM 檔以深入瞭解這些設定。
- 管理員裝置上面板 **應用程式** 特有的設定，例如桌布和 LED 指示器色彩。 只有 **面板應用程式** 的系統管理員可以存取這些設定。 由於 **面板應用程式** 設定可做為系統管理員設定的一部分使用，您必須具備裝置和 **面板應用程式** 的系統管理員登入認證，才能存取 **面板應用程式** 設定。

> [!NOTE]
> 透過裝置完成之 **面板應用程式** 設定的任何更新僅適用于該特定裝置。 這些更新不會影響您組織中的其他面板裝置。 例如，如果您從 [面板] **應用程式** 設定變更主畫面桌布影像，則只有該特定裝置的桌布影像才會變更。

### <a name="access-panels-app-settings"></a>Access 面板應用程式設定

您可以使用 [系統管理設定] 底下的 **[Teams** 系統管理設定] 選項來存取 **面板應用程式** 的特定設定。 存取 Teams 系統 **管理員設定的** 步驟可能會根據您裝置的 OEM 而有所不同。

若要存取 **Teams 系統管理員設定** 選項：

1. 點選主畫面上的 [ **設定]** 圖示。
2. 在 [ **設定] 畫面上** ，點選 [ **裝置設定]**。

    > [!NOTE]
    > 視您裝置的 OEM 而定，您可能需要立即或在下一個步驟之後輸入裝置系統管理員密碼。

3. 向下捲動以尋找 **Teams 系統管理設定** 選項。 點選它。

> [!NOTE]
> 有些 OEM 可能會以自己的自訂選項取代 **Teams 系統管理員設定** 選項。 如果您沒有看到 **[Teams 系統管理員設定** ] 選項，請查看您的裝置檔，以取得如何存取面板的系統管理員設定的指示。

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>將Teams 面板與 Android 上的 Microsoft Teams 會議室配對

若要在 Android 上配對Teams 面板和 Teams 會議室，這兩個裝置都必須登入相同的資源帳戶。

在Teams 面板上，使用您的系統管理員認證登入。

1. 移至 [ **裝置>設定] > Teams 系統管理設定>裝置配對]。**

2. Android 會議室顯示器前方的Teams 會議室上會顯示六位數的代碼。 在 Teams 面板上輸入代碼。  

#### <a name="enable-or-disable-meeting-check-in-and-automatic-room-release"></a>啟用或停用會議簽入和自動會議室發行

簽入和會議室發行設定可讓使用者在會議開始時所保留的會議室，存回 Teams 面板會議。 如果使用者在會議開始時間之後的一定時間內沒有存回，會議室便會釋出，可供其他人預約。

當 Teams 面板與 Android 上的 Microsoft Teams 會議室配對時，可以啟用簽入通知，以便在會議延遲時出現在會議前方顯示器上。

若要啟用簽入和會議室版本，請參閱 [Microsoft Teams 面板上的簽入和會議室發行](check-in-and-room-release.md)。

#### <a name="enable-or-disable-check-out-manual-room-release"></a>啟用或停用手動會議室發行 () 

啟用取出功能時，使用者可以使用Teams 面板手動釋出聊天室。 釋出聊天室會結束目前的預約，並讓其他人可以排程該聊天室。

此功能預設為停用，但可以每個裝置啟用。 若要啟用此功能，請移至 [ **設定>裝置設定] > Teams 系統管理員設定>會議** ]，然後開啟 [ **取出]**。

> [!NOTE]
> 如果配對的Teams 會議室裝置正在進行通話，則無法使用Teams 面板釋出聊天室。

#### <a name="enable-or-disable-room-reservations"></a>啟用或停用會議室預約

啟用會議室預約時，使用者可以使用Teams 面板來預約目前可用的會議室。 [保留 **] 按鈕點** 選時即開始保留，其持續時間可以 15 分鐘為增量，最長可達下一次保留的開始時間，或最多 24 小時。

此功能預設為啟用，但可以每個裝置停用。 若要停用此功能，請移至 [ **設定>裝置設定] > Teams 系統管理員設定>會議** ]，然後開啟 [ **停用會議室預約]**。

#### <a name="enable-or-disable-extension-of-existing-room-reservations"></a>啟用或停用現有會議室保留的擴充功能

啟用會議室預約擴充功能時，如果在預約的原始結束時間之後可以使用該聊天室，使用者就可以使用Teams 面板來擴充會議室的現有預約。 預約可在下一場會議開始時間前以 15 分鐘為增量，或未來最多可延長 24 小時，以時間較早者為准。

此功能預設為停用，但可以每個裝置啟用。 若要啟用此功能，請移至 [ **設定>裝置設定] > Teams 系統管理員設定>會議** ]，然後開啟 [ **延伸會議室保留]**。

#### <a name="enable-or-disable-room-capacity-warnings"></a>啟用或停用會議室容量警告

在 Android 上與 Teams 會議室配對的 Teams 面板，當聊天室的容量超過或超過容量時，可能會顯示警告訊息。 若要使用此功能，Teams 會議室必須具有支援使用者計數的相機。 Teams 會議室 Android 支援會議室容量警告，沒有Teams 面板。

會議室容量警告預設為停用，但可以每個裝置啟用。 若要啟用此功能，請執行下列動作：

1. 依照在[Android 上將Teams 面板與 Microsoft Teams 會議室配對](#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)中的步驟進行。 面板和 Teams 會議室裝置必須登入相同的資源帳戶。
2. 移至 [ **設定] > [裝置設定] > Teams 系統管理員設定>會議** 並開啟 **[最大會議室] 通知**。

#### <a name="enable-or-disable-viewing-of-room-equipment"></a>啟用或停用檢視會議室設備

當此功能開啟時，使用者可以檢視Teams 面板空間中可用的設備。

此功能預設為關閉，而且可在每個裝置上啟用。 若要將它開啟，請使用 PowerShell 中的[Set-Place](/powershell/module/exchange/set-place)來設定 、 `DisplayDeviceName` 、、 `VideoDeviceName` 及 `Tags` `IsWheelChairAccessible` 的顯示名稱 `AudioDeviceName` 。

或者，您可以在 Exchange 系統管理中心啟用這項功能。 如 [需詳細資訊，](/exchange/recipients-in-exchange-online/manage-resource-mailboxes#edit-a-resource) 請參閱編輯資源。

#### <a name="update-the-wallpaper"></a>更新桌布

變更主畫面桌布影像。

1. [存取 **Teams 系統管理設定**](#access-panels-app-settings)。
2. 點選 **[桌布]**。
3. 從 **[選擇您的影像**] 中，選取要設定為主畫面背景影像的影像。 在 [背景] 底下預覽選取的 **影像**。
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="此螢幕擷取畫面會顯示桌布設定畫面。":::
4. 返回到主畫面，並確認桌布已更新。

#### <a name="change-the-busy-state-led-color"></a>變更忙碌狀態 LED 色彩

系統管理員可以選擇紅色或紫色做為 LED 色彩，表示會議空間為忙碌或保留。 表示可用空間的 LED 色彩一律是綠色，無法變更。

1. [存取 **Teams 系統管理設定**](#access-panels-app-settings)。
2. 點 **選 [LED 設定]**。
3. 從 **[選擇您的 LED 色彩**] 中，選取您想要的色彩。
:::image type="content" source="../media/panels-led-settings.png" alt-text="此螢幕擷取畫面顯示 LED 色彩忙碌狀態設定。":::
4. 返回到主畫面，並確認忙碌狀態的 LED 色彩已更新。 如果目前可用的會議空間，請嘗試排程測試會議，以確認 LED 色彩對於忙碌狀態的變更。

## <a name="frequently-asked-questions"></a>常見問題集

尋找 Teams 面板裝置常見問題的解答。

**我未來還能看到會議空間的排程詳細資料嗎？**  
在主畫面右下)  (的 [ **預定行事曆** ] 磚中，您可以查看會議空間的排程詳細資料，從目前這一小時起，未來最多 24 小時。

**我是否可以從 Teams 面板裝置預約會議空間供日後使用？**  
否，您無法從面板預約會議空間供日後使用。 開始時間一定是從面板排程臨時會議的目前時間。

**我可以為臨時會議保留可用的會議空間多久？**  
您可以從目前時間開始保留可用的會議空間，直到下一個排程的會議時間，或從目前這小時算起最多 24 小時，以較早的時間為准。 例如，如果目前時間是上午 10 點，而下一個會議的開始時間是下午 2 點，您可以從上午 10 點到下午 2 點保留會議空間。
