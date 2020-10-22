---
title: Teams 中使用者的目前狀態
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 瞭解團隊中的目前狀態和目前狀態功能的管理設定。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fd066fe06126043475a7264b3b2c4501c7ac3ae
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650946"
---
# <a name="user-presence-in-teams"></a>Teams 中使用者的目前狀態

[目前狀態] 是 Microsoft 團隊 (與整個 Microsoft 365 或 Office 365) 中使用者設定檔的一部分。 [目前狀態] 表示使用者目前的可用性與其他使用者的狀態。 依預設，貴組織中任何有使用 Teams 的人都可以 (幾乎即時) 查看其他使用者是否在線上。 當您重新整理行動裝置上的頁面時，目前狀態會在網頁和桌上出版本上即時更新。

 > [!Note]
 > 如需不同平臺上團隊使用者設定檔的詳細資訊，請參閱 [依平臺的團隊功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="presence-states-in-teams"></a>Teams 中的目前狀態

|使用者設定|應用程式設定|
|:--- |:---|
| ![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) 有空|![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) 有空|
|| ![空心圓圈綠色核取記號，表示外出並有空](media/Presence_Available_OOF.png) 可用、不在辦公室。 注意：在使用者設定「自動回復」的時段內，系統會自動設定 [不在辦公室]。 如果使用者在這段時間內使用 app，可能會顯示雙重目前狀態，例如「不在辦公室」。 |
|  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) 忙碌 |  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) 忙碌  |
|| ![紅色實心圓圈，表示通話中忙碌](media/Presence_Busy.png) 通話中|
|| ![紅色實心圓圈，表示會議中忙碌](media/Presence_Busy.png) 會議中 |
|| ![紅色空心圓圈，表示忙碌](media/Presence_Busy_OOF.png) 通話中，外出|
|  ![紅色圓圈加白線，表示請勿打擾](media/Presence_DND.png) 請勿打擾 ||
|| ![紅色圓圈加白線，表示簡報中](media/Presence_DND.png) 簡報中|
|| ![紅色圓圈加白線，表示專注](media/Presence_DND.png) 致力. 當使用者在其行事曆中的 MyAnalytics/真知灼見中排程焦點時間時，就會發生焦點。|
| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) 離開| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) 離開|
|| ![黃色時鐘圖示，表示離開](media/Presence_Away.png)上次看到的*時間*|
|![黃色時鐘圖示，表示離開，馬上回來](media/Presence_Away.png) 馬上回來| |
|![灰色圓圈帶 x，表示離線](media/Presence_Offline.png) 顯示為離線。 在團隊即將推出。|![灰色圓圈帶 x，表示離線](media/Presence_Offline.png) 處於.  如果使用者沒有在任何裝置上登入，幾分鐘後，就會顯示為離線。 | |
|| ![空心灰色圓圈，表示狀態不明](media/Presence_Unknown.png) 狀態不明|
|| ![紫色圓圈加箭號，表示外出](media/Presence_OOF.png) [不在辦公室]。 當您設定自動回復時，就會使用 [不在辦公室]。  (僅適用于 Outlook。 )  |
|||

App 設定的目前狀態是以使用者活動 (提供，離開) ，Outlook 行事曆狀態 (在會議) 中，或團隊 app 的狀態 (在通話中，提出) 。 當您是以您的行事曆為基礎的焦點模式 **時，焦點** 會是人員在團隊中看到的狀態。 焦點模式將在其他產品中顯示為 [ **請勿打擾** ]。

當您鎖定電腦或電腦進入 [空閒] 或 [睡眠] 模式時，您的目前狀態會變更為 [離開]。 在行動裝置上，只要團隊 app 在背景中，您的目前狀態就會變更為 [離開]。

不管使用者目前狀態為何，都會收到所有在 Teams 中傳送給他們的聊天訊息。 如果他人傳送郵件給使用者時使用者已離線，聊天訊息會在使用者下次上線時顯示在 Teams 中。 如果使用者狀態設定為 [請勿打擾]，使用者仍會收到聊天訊息，但不會顯示橫幅通知。

使用者會在除了 [請勿打擾] 以外的所有目前狀態狀態中接收來電，讓來電移至語音信箱。 如果受話方封鎖來電者，通話將不會傳送，且來電者看到的受話方目前狀態是「離線」。

使用者可以到 Teams 的 [設定]****  >  [隱私權]****，將人員新增至其優先存取清單。 即使使用者的狀態設定為 [請勿打擾]，擁有優先順序存取權的人員也可以與使用者聯繫。

### <a name="dual-presence"></a>雙重目前狀態

  對於大多數使用者而言，目前狀態的運作方式是由行事曆或裝置事件（例如通話）中的事件所導致。 使用者可以透過手動設定狀態（有一些到期時間），在 UI 中覆寫此狀態。

## <a name="user-configured-states-expiration"></a>使用者設定的狀態到期日

當使用者選取特定的目前狀態時，它會優先于任何 app 活動更新。 例如，如果使用者將自己設為 [請勿打擾]，即使她出席會議或接聽電話，她的目前狀態仍會保留為 [請勿打擾]。

使用者設定的狀態在 [團隊] 中有預設的到期設定，以避免使用者顯示在一段時間之後可能不相關的狀態。

|使用者設定的狀態|預設到期日|
|:--- |:---|
| 忙碌|1天|
| 請勿打擾|1天|
| 公司|7天|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>比較商務用 Skype 與 Teams 中的管理設定

下列的商務用 Skype 管理設定與 Teams 不同：

- 在 Teams 中，組織的使用者一律啟用目前狀態共用。 隱私權 (您可以在此定義哪些人員可以查看目前狀態) 設定無法在團隊中取得。
- Teams 中的使用者一律啟用與所有人 (包括同盟服務) 共用目前狀態。 他們的連絡人清單 (如果他們在商務用 Skype 中有此清單) 會顯示在 [聊天] > [連絡人]**** 底下或在 [通話] > [連絡人]**** 底下。
- Teams 中的使用者一律啟用用戶端的「請勿打擾」和「突破」功能。
- 當 Teams 與 Outlook 整合時，一律為使用者啟用行事曆 (包括外出和其他行事曆資訊) 整合。
- 如果組織也使用商務用 Skype，Teams 中的使用者一律啟用 [上次看到]** 或 [離開時間]**。

> [!NOTE]
> 目前不支援 Teams 系統管理員自訂這些設定的功能。

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>團隊中與 Microsoft Outlook 比較的管理員設定

Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。

如果使用者帳戶的 [升級模式] 原則設定為 [TeamsOnly]，Outlook 就會與團隊進行交談，以取得目前狀態。 如果使用者帳戶未設為 TeamsOnly，Outlook 就會與商務用 Skype 交談。

## <a name="coexistence-with-skype-for-business"></a>與商務用 Skype 共存

請參閱 [與商務用 Skype 共存](coexistence-chat-calls-presence.md) ，以取得貴組織也使用商務用 skype 時，小組目前狀態如何運作的詳細資料。
