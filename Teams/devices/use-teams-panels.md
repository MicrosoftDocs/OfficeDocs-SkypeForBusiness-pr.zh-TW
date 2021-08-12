---
title: 如何使用Microsoft Teams面板裝置
ms.author: serdars
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
description: 本文提供如何使用面板Teams指南。
ms.openlocfilehash: d7f7e34bec83d8d1debeed39eeed162e98d011ac3656517025005ce31db24b65
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848078"
---
# <a name="how-to-use-microsoft-teams-panels"></a>如何使用Microsoft Teams面板

Microsoft Teams面板是安裝在會議空間外部的精簡數字顯示裝置，通常位於入口旁邊。 這些觸控螢幕面板Microsoft Teams專用裝置，可提供會議空間和排定會議概覽。 使用生動的色彩編碼 LED 和首頁螢幕指示器，您可以判斷空間是否可用或保留距離。 您可以使用Teams面板，為臨時會議保留可用的會議空間。

Teams面板裝置會預先安裝 Microsoft Teams，並顯示透過 Outlook 或 Teams 排程的會議詳細資料。

本文為使用者和系統管理員提供如何使用面板Teams指南。 它也提供有關使用這些裝置 [之](#frequently-asked-questions) 常見問題的解答。

若要概觀面板裝置，以及如何在組織中規劃、傳遞和管理這些裝置，請參閱部署Microsoft Teams[面板](teams-panels.md)。

有關快速入門，請查看開始使用[Teams面板](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)。

## <a name="teams-panels-end-user-experience"></a>Teams面板的使用者體驗

探索[會議面板裝置Teams](#explore-teams-panels-home-screen)畫面，以查看會議空間和會議詳細資料。 或者，點一下觸控螢幕面板並捲動以執行其他動作。

使用您的Teams面板裝置：

- [查看會議空間詳細資料與可用性、會議詳細資料、預定的預約](#explore-teams-panels-home-screen)
- [保留可用的會議空間](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [報告問題](#report-a-problem)
- [查看或更新裝置設定](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>探索Teams面板首頁畫面

主畫面是螢幕面板裝置的主要視覺Teams介面。  

您可以在主畫面中查看位置和會議詳細資料、保留空間、查看預定，以及識別目前的可用性狀態。

下列螢幕擷取畫面顯示主畫面上不同的元件Teams磚：

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="此螢幕擷取畫面顯示主畫面Teams畫面上的不同區域":::

請參閱下表，瞭解每個磚的描述：

瓦 | 描述
:---|:---
**1-目前時間、日期、日期和會議空間詳細資料** | 顯示目前的時間、日期、日期和會議空間名稱。 會議空間名稱是已登錄面板的資源帳戶名稱。
**2-會議空間可用性和會議詳細資料** | 指出會議空間的可用性，並顯示會議詳細資料。 請參閱 [會議空間可用性和會議詳細資料磚](#meeting-space-availability-and-meeting-details-tile)。
**3-即將推出的日曆** | 顯示會議空間的日曆和目前時間起最多 24 小時的可用時間。 向上或向下卷起以判斷哪些時段可用，哪些時段是保留的。
**4-設定** | 顯示設定 **圖示**。 點一下以報告問題或更新可用的裝置設定。

### <a name="meeting-space-availability-and-meeting-details-tile"></a>會議空間可用性和會議詳細資料磚

此磚的外觀及其功能會視會議空間可用性和預約類型而異。

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>已為排定的會議保留會議空間

此磚會以紫色顯示，以紫色表示會議空間，而會議空間是透過 (或 Outlook 排定的會議空間Outlook Teams) 。 它會以醒目的文字顯示會議標題、會議開始時間和結束時間，以及會議召集人的名稱。 對於會議Teams，Teams也會顯示該標誌。 當會議詳細資料醒目顯示時，出席者可以輕鬆地確認他們位於正確的會議空間、正確的時間，以及適合的會議。

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams面板首頁畫面，顯示會議空間已保留為排定的會議":::

> [!NOTE]
>
> - 排程會議之後，最多可能需要 90 秒的時間，才能同步的日曆，並反映在面板畫面上。
> - 針對 [標示為私人的](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d)排定會議，會顯示私人 **會議** ，而不是實際會議標題。

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>為臨時會議保留會議空間

為臨時會議保留的會議空間，磚會以紫色 [顯示](#reserve-meeting-spaces-for-ad-hoc-meetings)。 它會以 **醒目** 的文字顯示保留，以及會議開始時間和結束時間。 臨時會議會自動排程為Teams，因此Teams標誌一直會出現在螢幕上。

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams面板主畫面，顯示會議空間已保留為臨時會議":::

#### <a name="meeting-space-is-available"></a>會議空間可供使用

磚會以綠色顯示，以表示可用的會議空間。 它會以 **醒目** 的文字顯示可用，而且也會顯示一個保留按鈕，您可以點選以保留臨時會議 [的會議空間](#reserve-meeting-spaces-for-ad-hoc-meetings)。 您可以檢查會議空間的近期 (右下) ，以決定臨時會議結束時間。

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="此螢幕擷取畫面顯示Teams會議室可用時，主畫面的顯示方式":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>為臨時會議保留會議空間

您可以直接從面板 [為](#meeting-space-is-available) 臨時會議保留可用的會議空間。 所有臨時會議都會自動排程為Teams會議。 不過，一旦保留之後，您無法透過面板釋出或取消保留會議空間。 只有裝置資源帳戶的系統管理員可以透過 (或 Outlook Teams取消) 臨時會議) 取消空間。

對於直接從面板預約的臨時會議：

- 開始時間一直是目前的時間，因此，您無法將時間排程到未來時間。
- 結束時間可以是直到下一個排定的會議，或從目前時間起最多 24 小時 ，以較早者為准。 檢查 **主畫面上的** 下一個日曆磚，以決定會議空間可供使用或預約的時段。

若要為臨時會議保留可用的會議空間：

1. 在主畫面上， **點選保留** 按鈕。
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams顯示保留按鈕的首頁畫面":::
2. 在 **臨時會議畫面** 中，查看可用的結束時間選項。 您可以使用向右或向左箭鍵流覽可用的結束時間選項。

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="顯示結束時段的臨時會議畫面":::

    > [!Note]
    >
    > - 結束時間選項會以一小時的 15 分鐘間隔顯示。
    > - 結束時間預設為目前時間之後至少五分鐘的下一個 15 分鐘間隔。 例如，如果目前的時間是下午 1：57，則預設結束時間會顯示為下午 2：15，而不是下午 2：00。 這可防止使用者預約 5 分鐘以內的空間。 在上方螢幕擷取畫面中，預設結束時間會顯示為下午 2：00，這是目前時間 (1：53 pm) 之後至少 15 分鐘的間隔。
    > - 上述規則的例外是，下一個會議開始時間從目前時間起不到五分鐘。 在這種情況下，您可以預約空間，直到下一個會議開始時間。 例如，如果目前的時間是下午 1：57，而下一個會議開始時間是下午 2：00，則 2：00 PM 會顯示為唯一的結束時間選項，您可以將空間保留三分鐘。

3. 點一下所需的結束時間間隔， **然後點一** 下保留 。

    確認視窗會以大拇指顯示圖釋、會議開始時間和結束時間，以及會議空間名稱。
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="臨時會議確認訊息":::
現在，主畫面上的右側磚會以紫色顯示，並顯示保留文字和 Teams標誌。 這表示會議空間現在已保留為臨時會議Teams空間。
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="顯示會議空間為臨時會議保留的主畫面":::

    > [!NOTE]
    > 如果會議室是會議室Microsoft Teams，您可以使用會議室Teams會議室或裝置Microsoft Teams加入Surface Hub會議。

### <a name="report-a-problem"></a>報告問題

若要報告裝置或會議空間的問題、要求功能更新，或提供任何意見回應，請使用主畫面上的設定圖示。 

1. 點設定 **畫面** 上的齒輪圖示。

2. 點選 **報告問題** 選項。

    傳送 **意見回饋** 畫面會以表單格式顯示。
3. 從輸入 **下** 拉式清單中選擇要求類型。
4. 從問題 **下** 拉清單選取類別。
5. 在標題 **文字** 欄位中，使用面板鍵盤輸入標題。
6. 如有需要，在 **標題** 下方的文字欄位中輸入其他詳細資料。

    > [!NOTE]
    > 請勿包含任何個人識別資訊。

7. 請閱閱您的專案， **然後點** 一下傳送 。

### <a name="view-or-update-a-device-setting"></a>查看或更新裝置設定

您可以直接從面板查看或更新數個裝置設定，例如關於、協助工具、重新開機和隱私權政策。 可用的裝置設定可能會依據您裝置的原始設備製造商 (OEM) 不同。 有關您裝置特定設定的資訊，請參閱 OEM 檔。

若要查看或更新裝置設定：

1. 點設定 **畫面** 上的圖示。
2. 在畫面設定，點一下 **裝置設定**。
3. 在裝置 **設定** 畫面中，點一下您想要查看或更新的設定。
4. 請遵循畫面上的提示來查看或更新設定。

## <a name="teams-panels-admin-experience"></a>Teams面板系統管理員體驗

如果您是面板資源帳戶Teams系統管理員，[](teams-panels.md\#resource-account-provisioning)則您也是裝置上的 **Panels App** 系統管理員。 作為 **Panels App** 系統管理員，除了管理裝置上的 **Panels** App [](#teams-panels-end-user-experience)設定之外，您還可以執行使用者經驗區段提及的所有功能。

您的面板裝置提供兩種類型的系統管理設定。 您必須是裝置系統管理員才能存取可用的系統管理員設定。 使用者無法存取這些設定。

- 裝置特有的系統管理設定，例如顯示、時間和日期、語言、藍牙、WiFi 等。 請參閱 OEM 檔以進一瞭解這些設定。
- 您裝置上的 **[面板應用程式** 」 特有的系統管理設定，例如牆紙和 LED 指示器色彩。 只有 **Panels App 的系統管理員** 才能存取這些設定。 由於 **Panels App** 設定是系統管理設定的一部分，因此您必須擁有裝置和 **面板** App 的系統管理員登錄認證，才能存取 **面板 App** 設定。

> [!NOTE]
> 透過裝置對 **Panels App** 設定所做的任何更新僅適用于該特定裝置。 這些更新不會影響貴組織的其他面板裝置。 例如，如果您從 [面板應用程式設定> 變更[主畫面畫面圖片影像，只會針對該特定裝置變更牆紙影像。

### <a name="access-panels-app-settings"></a>Access Panels App 設定

您可以使用系統管理 **設定** 下的面板應用程式設定面板 **應用程式** 選項存取特定設定。 存取面板 App **設定可能會根據您的** 裝置 OEM 而不同。

若要存取 **面板應用程式設定** 選項：

1. 點設定 **畫面** 上的圖示。
2. 在畫面 **設定，** 點一下 **裝置設定**。
3. 點一下 **系統管理設定。**

    > [!NOTE]
    > 視您裝置 OEM 的不同，您可能需要在現在或下一個步驟之後輸入裝置系統管理員密碼。

4. 向下卷起以尋找 **面板應用程式設定** 選項。 點一下。
5. 點選 **右設定** 上的面板應用程式按鈕。
    畫面會顯示可用的 **面板應用程式** 設定。

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="此螢幕擷取畫面顯示幕幕，以及可用的面板應用程式設定":::

    使用此螢幕來更新您裝置下列 **的面板** 應用程式設定：

    - [壁紙](#update-the-wallpaper)
    - [LED 指示器](#change-the-busy-state-led-color)

#### <a name="update-the-wallpaper"></a>更新牆紙

變更主畫面的牆紙影像。

1. [Access **Panels App 設定。**](#access-panels-app-settings)
2. 點 **一下 [牆紙**> 。
3. 從 **選擇您的影像**，選取要設為主畫面背景影像的影像。 預覽背景下的選取 **影像**。
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="此螢幕擷取畫面顯示牆紙設定畫面":::
4. 返回 [主畫面>，並確認已更新牆紙。

#### <a name="change-the-busy-state-led-color"></a>變更忙碌狀態 LED 色彩

系統管理員可以選擇紅色或紫色作為 LED 色彩，以表示會議空間忙碌或已保留。 表示可用空間的 LED 色彩一直為綠色，且無法變更。

1. [Access **Panels App 設定。**](#access-panels-app-settings)
2. 點 **設定**。
3. 從 **選擇您的 LED 色彩**，選取所需的色彩。
:::image type="content" source="../media/panels-led-settings.png" alt-text="此螢幕擷取畫面顯示 LED 色彩忙碌狀態設定":::
4. 返回主畫面，並確認忙碌狀態的 LED 色彩已更新。 如果會議空間目前可用，請嘗試排程測試會議，以驗證忙碌狀態 LED 色彩的變更。

## <a name="frequently-asked-questions"></a>常見問題集

尋找有關面板裝置Teams問題的解答。

**我未來可以看到會議空間的排程詳細資料有多遠？**  
在主畫面 (右下) 的即將到來的日曆磚中，您可以看見會議空間的排程詳細資料，從目前時間起，未來最多 24 小時。

**我可以從面板裝置為Teams空間嗎？**  
否，您無法從面板保留未來時間的會議空間。 開始時間一直是從面板排程的臨時會議目前時間。

**我可以為臨時會議保留可用會議空間多久？**  
您可以保留從目前時間開始到下一個排定的會議時間，或從目前時間起最多 24 小時的可用會議空間，以較早者為准。 例如，如果目前的時間是上午 10 點，而下一個會議開始時間是下午 2 點，您可以將會議空間從上午 10 點保留到下午 2 點。
