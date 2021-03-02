---
title: 如何使用 Microsoft Teams 面板裝置
ms.author: v-mdhiman
author: ManikaDhiman
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
search.appverid: MET150
localization_priority: Normal
description: 本文提供如何使用 Teams 面板裝置之指引。
ms.openlocfilehash: eba450b42bb66dfbe202290cdd235a0d4db9e710
ms.sourcegitcommit: 6785d7f1ef5d2010ab334ec8cc46884327a53662
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2021
ms.locfileid: "50395324"
---
# <a name="how-to-use-microsoft-teams-panels"></a>如何使用 Microsoft Teams 面板

Microsoft Teams 面板是小型的數字顯示裝置，安裝在會議空間外，通常位於進入處旁邊。 這些觸控螢幕面板是專用的 Microsoft Teams 裝置，可快速查看您的會議空間和已排程會議。 使用生動的色彩編碼 LED 和主畫面指示器，您可以判斷空間是否可用或保留距離。 您可以使用 Teams 面板，為臨時會議保留可用的會議空間。

Teams 面板裝置會預先安裝 Microsoft Teams，並顯示透過 Outlook 或 Teams 日曆排程的會議詳細資料。

本文提供使用者和系統管理員如何使用 Teams 面板裝置之指引。 它也提供有關使用這些 [裝置之常見問題](#frequently-asked-questions) 的解答。

若要瞭解面板裝置概觀，以及如何在貴組織中規劃、傳遞及管理這些裝置，請參閱 [部署 Microsoft Teams 面板](teams-panels.md)。

有關快速入門，請查看 Teams[面板的開始使用。](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

## <a name="teams-panels-end-user-experience"></a>Teams 面板使用者體驗

探索 Teams [面板裝置](#explore-teams-panels-home-screen) 中的主畫面，以查看會議空間和會議詳細資料。 或者，點一下觸控螢幕面板並捲動以執行其他動作。

使用您的 Teams 面板裝置：

- [查看會議空間詳細資料與可用性、會議詳細資料、預定預定](#explore-teams-panels-home-screen)
- [保留可用的會議空間](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [報告問題](#report-a-problem)
- [查看或更新裝置設定](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>探索 Teams 面板首頁畫面

主畫面是 Teams 面板裝置的主要視覺介面。  

在主畫面中，您可以查看位置和會議詳細資料、預約空間、查看預定預定，以及識別目前的顯示狀態。

下列螢幕擷取畫面顯示 Teams 面板首頁畫面上的不同部分或磚：

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="此螢幕擷取畫面顯示 Teams 面板首頁畫面上的不同區域":::

請參閱下表，瞭解每個磚的描述：

瓦 | 說明
:---|:---
**1-目前的時間、日期、日期及會議空間詳細資料** | 顯示目前的時間、日期、日期及會議空間名稱。 會議空間名稱是已登錄至面板的資源帳戶名稱。
**2 會議空間可用性和會議詳細資料** | 表示會議空間可用性，並顯示會議詳細資料。 查看 [會議空間可用性和會議詳細資料磚](#meeting-space-availability-and-meeting-details-tile)。
**3-近期的日曆** | 顯示從目前時間起最多 24 小時的會議空間日曆和可用性。 向上或向下卷卷來判斷哪些時段可以使用，哪些時段是保留的。
**4-設定** | 顯示設定 **圖示** 。 點一下以報告問題或更新可用的裝置設定。

### <a name="meeting-space-availability-and-meeting-details-tile"></a>會議空間可用性和會議詳細資料磚

此磚的外觀及其功能會視會議空間可用性和預約類型而異。

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>已排程會議保留會議空間

針對透過 Outlook 或 Teams (排程的會議所保留的會議空間，磚會以紫色) 。 它會以醒目的文字顯示會議標題、會議開始與結束時間，以及會議召集人的名稱。 Teams 會議也會顯示 Teams 標誌。 當會議詳細資料醒目顯示時，出席者可以輕鬆地確認他們位於正確的會議空間、適當的時間，以及適當的會議。

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams 面板主畫面顯示會議空間已保留給已排程的會議":::

> [!NOTE]
>
> - 排程會議之後，最多可能需要 90 秒，才能同步的日曆，並反映在面板畫面上。
> - 針對[標示為私人的](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d)已排程會議，會顯示私人會議，而非實際會議標題。

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>會議空間會保留為臨時會議

針對臨時會議所保留的會議空間，磚會以紫色 [顯示](#reserve-meeting-spaces-for-ad-hoc-meetings)。 它會以 **醒目的文字** 顯示保留，以及會議開始與結束時間。 當您從面板中排程臨時 (而非 Outlook 或 Teams) 時，您實際上會預約該會議空間的日曆。 這類會議會自動排程為 Teams 會議，因此 Teams 標誌永遠會出現在螢幕上。

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams 面板主畫面顯示會議空間已保留給臨時會議":::

#### <a name="meeting-space-is-available"></a>會議空間可供使用

磚會以綠色顯示，以用於可用的會議空間。 它會以 **醒目** 的文字顯示可用，同時會出現一個保留按鈕，您可以點選以保留臨時 [會議的會議空間](#reserve-meeting-spaces-for-ad-hoc-meetings)。 您可以在右下圖磚 (會議空間的近期) 決定臨時會議結束時間。

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="此螢幕擷取畫面顯示當會議空間可用時，Teams 面板主畫面的顯示方式":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>為臨時會議保留會議空間

您可以直接從面板 [預訂](#meeting-space-is-available) 可用的會議空間，以召開臨時會議。 所有臨時會議都會自動排程為 Teams 會議。 不過，一旦保留後，您即無法透過面板釋放或取消保留該會議空間。 只有裝置資源帳戶的系統管理員可以透過 Outlook 或 Teams (取消臨時會議，) 空間。

針對直接從面板預約的臨時會議：

- 開始時間一直是目前的時間，因此無法排程未來時間。
- 結束時間可以是直到下一個排定的會議，或從目前時間起最多 24 小時，以較早者為准。 在主 **畫面上檢查** 預定的日曆磚，以決定有可用或預約會議空間的時段。

若要保留臨時會議可用的會議空間：

1. 在主畫面上， **點選保留** 按鈕。
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams 面板顯示保留按鈕的首頁畫面":::
2. 在 **臨時會議畫面** 中，查看可用的結束時間選項。 您可以使用向右或向左鍵來流覽可用的結束時間選項。

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="顯示結束時段的臨時會議畫面":::

    > [!Note]
    >
    > - 結束時間選項會以一小時的 15 分鐘間隔顯示。
    > - 結束時間預設為目前時間之後至少五分鐘的下一個 15 分鐘間隔。 例如，如果目前的時間是下午 1：57，預設的結束時間會顯示為 2：15 PM，而不是 2：00 PM。 這可防止使用者預約空間 5 分鐘以下。 在上一個螢幕擷取畫面中，預設的結束時間會顯示為下午 2：00，即目前時間 (下午 1：53 之後至少 15 分鐘) 。
    > - 上述規則的例外是，下一個會議開始時間從目前時間起不到五分鐘。 在這種情況下，您可以預約空間直到下一個會議開始時間。 例如，如果目前的時間是下午 1：57，而下一個會議開始時間是下午 2：00，則 2：00 PM 會顯示為唯一的結束時間選項，您可以將空間保留三分鐘。

3. 點一下所需的結束時間間隔，然後點一下 **保留**。

    確認視窗會以大拇指顯示 Emoji、會議開始與結束時間，以及會議空間名稱。
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="臨時會議確認訊息":::
主畫面上的右側磚現在會以紫色顯示，並顯示 **保留** 文字和 Teams 標誌。 這表示會議空間現在已保留為臨時 Teams 會議。
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="主畫面顯示會議空間已保留給臨時會議":::

    > [!NOTE]
    > 如果會議空間是 Microsoft Teams 會議室，您可以使用會議室中的 Microsoft Teams 會議室或 Surface Hub 裝置加入此 Teams 會議。

### <a name="report-a-problem"></a>報告問題

若要報告裝置或會議空間的問題、要求功能更新，或提供任何意見回饋，請使用主畫面上的設定圖示。 

1. 點一 **下主** 畫面上的設定齒輪圖示。

2. 點選 **報告問題** 選項。

    傳送 **意見回饋** 畫面會以表單格式顯示。
3. 從類型 **下** 拉式清單中選擇要求類型。
4. 從問題 **下** 拉清單選取類別。
5. 在標題 **文字** 欄位中，使用面板鍵台輸入標題。
6. 如有需要，在 **標題** 下方的文字欄位中輸入其他詳細資料。

    > [!NOTE]
    > 請勿包含任何個人識別資訊。

7. 請審查您的專案，然後 **點一** 下傳送。

### <a name="view-or-update-a-device-setting"></a>查看或更新裝置設定

您可以直接從面板中查看或更新多種裝置設定，例如協助工具、重新開機、隱私權原則。 可用的裝置設定可能會依據您裝置的原始設備製造商 (OEM) 不同。 有關您裝置特定設定的資訊，請參閱 OEM 檔。

若要查看或更新裝置設定：

1. 點一 **下** 主畫面上的設定圖示。
2. 在設定 **畫面中** ，點 **一下裝置設定**。
3. 在裝置 **設定** 畫面中，點一下要查看或更新的設定。
4. 請遵循畫面上的提示來查看或更新設定。

## <a name="teams-panels-admin-experience"></a>Teams 面板系統管理員體驗

如果您是 [Teams](teams-panels.md\#resource-account-provisioning)面板資源帳戶的系統管理員，那麼您也是裝置上 **面板應用程式的** 系統管理員。 做 **為面板 App** 系統管理員，除了管理裝置上的面板 **App** 設定之外 [](#teams-panels-end-user-experience)，您還可以執行使用者經驗區段提及的所有功能。

您的面板裝置提供兩種類型的系統管理設定。 您必須是裝置系統管理員，才能存取可用的系統管理員設定。 使用者無法存取這些設定。

- 裝置特有的系統管理設定，例如顯示、時間和日期、語言、藍牙、WiFi 等。 請參閱 OEM 檔，以進一瞭解更多這些設定。
- 您裝置上面板 **應用程式** 特有的系統管理設定，例如背景圖片和 LED 指示器色彩。 只有面板 **應用程式的系統管理員才能** 存取這些設定。 由於 **Panels App** 設定是做為系統管理設定一部分提供，您必須同時擁有裝置和 **面板** App 的系統管理員登錄認證，才能存取 **面板 App** 設定。

> [!NOTE]
> 透過裝置對 **面板應用程式** 設定所做的任何更新僅適用于該特定裝置。 這些更新不會影響貴組織的其他面板裝置。 例如，如果您從面板應用程式設定變更主畫面背景 **圖片，背景** 圖片影像只會針對該特定裝置變更。

### <a name="access-panels-app-settings"></a>Access 面板應用程式設定

您可以使用系統管理 **設定** 下的面板 **應用程式** 設定選項，存取特定面板 App 的設定。 存取面板 **應用程式設定的步驟** 可能會根據您的裝置 OEM 而不同。

若要存取 **面板應用程式設定** 選項：

1. 點一 **下** 主畫面上的設定圖示。
2. 在設定 **畫面上** ，點 **一下裝置設定**。
3. 點一下 **系統管理設定**。

    > [!NOTE]
    > 視您裝置 OEM 的不同，您可能需要在現在或下一個步驟之後輸入裝置系統管理員密碼。

4. 向下卷卷以尋找 **面板應用程式設定** 選項。 點一下。
5. 點選 **右畫面** 上的面板應用程式設定按鈕。
    畫面上會顯示可用的 **面板 App** 設定。

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="此螢幕擷取畫面顯示幕幕與可用的面板應用程式設定":::

    使用此畫面來更新您裝置中的下列面板 **App** 設定：

    - [壁紙](#update-the-wallpaper)
    - [LED 指示器](#change-the-busy-state-led-color)

#### <a name="update-the-wallpaper"></a>更新背景圖片

變更主畫面背景圖片。

1. [Access **面板應用程式設定**](#access-panels-app-settings)。
2. 點 **一下 [背景圖片**。
3. 從 **選擇影像，** 選取要設為主畫面背景影像的影像。 在背景下預覽選取 **的影像**。
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="此螢幕擷取畫面顯示背景圖片設定畫面":::
4. 回到主畫面，並確認背景圖片已更新。

#### <a name="change-the-busy-state-led-color"></a>變更忙碌狀態 LED 色彩

系統管理員可以選擇紅色或紫色作為 LED 色彩，表示會議空間忙碌或已預訂。 表示可用空間的 LED 色彩永遠為綠色，無法變更。

1. [Access **面板應用程式設定**](#access-panels-app-settings)。
2. 點 **一下 LED 設定**。
3. 從 **選擇您的 LED 色彩**，選取想要的色彩。
:::image type="content" source="../media/panels-led-settings.png" alt-text="此螢幕擷取畫面顯示 LED 色彩忙碌狀態設定":::
4. 回到主畫面，並確認忙碌狀態的 LED 色彩已更新。 如果會議空間目前可用，請嘗試排程測試會議，確認忙碌狀態 LED 色彩的變更。

## <a name="frequently-asked-questions"></a>常見問題集

尋找 Teams 面板裝置常見問題的解答。

**我未來可以看到會議空間的排程詳細資料嗎？**  
在主畫面 (右下角的) 中，您可看到從目前時間起，未來最多 24 小時的會議空間排程詳細資料。

**我可以從 Teams 面板裝置預訂未來的會議空間嗎？**  
否，您未來無法從面板保留會議空間。 開始時間一直是從面板排程之臨時會議的時間。

**我可以為臨時會議保留可用會議空間多久？**  
您可以預約從目前時間開始到下一個排定的會議時間，或從目前時間起最多 24 小時 ，以較早的時間為准。 例如，如果目前的時間是上午 10 點，而下一個會議開始時間是下午 2 點，您可以將會議空間從上午 10 點保留到下午 2 點。