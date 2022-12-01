---
title: Teams 中使用者的目前狀態
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 瞭解 Teams 中的 [目前狀態] 及 [目前狀態] 功能的系統管理設定。
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f2969af142828ca5d478f29f2afee319ada91b7
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198585"
---
# <a name="user-presence-in-teams"></a>Teams 中使用者的目前狀態

顯示狀態是使用者在 Microsoft Teams (以及整個 Microsoft 365 或 Office 365) 的一部分。 [目前狀態] 表示使用者目前的可用性與其他使用者的狀態。 依預設，貴組織中任何有使用 Teams 的人都可以 (幾乎即時) 查看其他使用者是否在線上。 當您重新整理行動裝置上的頁面時，線上和傳統版會即時更新 [目前狀態]。

 > [!NOTE]
 > 如需有關不同平台上 Teams 使用者設定檔的詳細資訊，請參閱[依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

 > [!NOTE]
 > Teams 會尊重您的隱私權設定，因此如果您已啟用隱私權模式，外部使用者將不會看到您的目前狀態。

## <a name="presence-states-in-teams"></a>Teams 中的目前狀態


|使用者設定|應用程式設定|
|:--- |:---|
| ![實心綠色核取記號，顯示目前狀態為有空。](media/Presence_Available.png) 有空|![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) 有空|
|| ![空心綠色核取記號，表示不在辦公室。](media/Presence_Available_OOF.png) 有空，外出。 附注：在使用者設定「自動回復」的期間內，系統會自動設定為 [外出]。 如果使用者是在這些時段內使用應用程式，可能會顯示雙重顯示 (例如「外出，有空」)。 |
|  ![紅色實心圓圈，表示忙碌。](media/Presence_Busy.png) 忙碌 |  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) 忙碌  |
|| ![紅色實心圓圈，表示通話中忙碌。](media/Presence_Busy.png) 通話中|
|| ![紅色實心圓圈，表示會議中忙碌。](media/Presence_Busy.png) 會議中 |
|| ![紅色空心圓圈，表示忙碌。](media/Presence_Busy_OOF.png) 通話中，外出|
|  ![紅色圓圈加白線，表示請勿打擾。](media/Presence_DND.png) 請勿打擾 ||
|| ![紅色圓圈加白線，表示簡報中。](media/Presence_DND.png) 簡報中|
|| ![紅色圓圈加白線，表示專注。](media/Presence_DND.png) 專注。 當使用者在行事曆中排程 [MyAnalytics/Insights] 時，就會進入 [專注] 功能。|
| ![黃色時鐘圖示，表示離開。](media/Presence_Away.png) 離開| ![黃色時鐘圖示，表示離開。](media/Presence_Away.png) 離開|
|| ![黃色時鐘圖示，表示離開](media/Presence_Away.png)上次看到的 *時間*|
|![黃色時鐘圖示，表示離開，馬上回來。](media/Presence_Away.png) 馬上回來| |
|![灰色圓圈帶 x，表示離線。](media/Presence_Offline.png) 顯示為離線|![灰色圓圈帶 x，表示離線](media/Presence_Offline.png) 離線。  當使用者未在任何裝置上登入達數分鐘，便會顯示為 [離線]。 |
|| ![空心灰色圓圈，表示狀態不明。](media/Presence_Unknown.png) 狀態不明|
|| ![紫色圓圈加箭號，表示外出。](media/Presence_OOF.png) 外出。 設定為自動回復時，會使用 [外出] 功能。 |

 > [!NOTE]
 > 對於擁有其信箱託管於內部部署的使用者，預期目前狀態延遲為一小時 (最大值)。

應用程式設定的目前狀態是根據使用者活動 (有空、離開)、Outlook 行事曆狀態 (會議中)、或是 Teams 應用程式狀態 (通話中、簡報中)。 當您在行事曆中使用 [焦點模式] 時，人員會在 Teams 上看到顯示為 **[專注中]** 的狀態。 在其他產品中，焦點模式會顯示為 **請勿打擾**。

當您鎖定電腦或當您的電腦進入閒置或睡眠模式時，您目前的顯示狀態會變更為 [離開]。 在行動裝置上，只要 Teams 應用程式在背景作業時，您的顯示狀態即會變更為 [離開]。

不管使用者目前狀態為何，都會收到所有在 Teams 中傳送給他們的聊天訊息。 如果他人傳送郵件給使用者時使用者已離線，聊天訊息會在使用者下次上線時顯示在 Teams 中。 如果使用者狀態設為 [請勿打擾]，使用者仍然會收到交談訊息，但不會顯示橫幅通知。

使用者在所有狀態下都會收到通話，但「請勿打擾」狀態除外，在這種狀態下，通話會送往他們的語音信箱。 如果受話方封鎖來電者，通話將不會傳送，且來電者看到的受話方目前狀態是「離線」。

使用者可以到 Teams 的 [設定]  >  [隱私權]，將人員新增至其優先存取清單。 具有優先存取的人員可以與使用者聯繫，即使該使用者的狀態設定為 [請勿打擾]。

### <a name="dual-presence"></a>雙重狀態

  目前的方式適用于多數使用者，是由行事曆或裝置事件中的事件 (例如通話) 所促成。 使用者可以手動設定狀態(且該設定具有一段到期時間)以在 UI 中覆寫此狀態。

## <a name="user-configured-states-expiration"></a>使用者已設定狀態到期日

當使用者選取特定的目前狀態時，它會優先于所有應用程式活動更新。 例如，如果使用者將自己設定為「請勿打擾」，則即使她出席會議或應答通話，其目前狀態仍然會維持為「請勿打擾」。

使用者設定的狀態在 Teams 中有預設的到期設定，以避免使用者在一段時間後可能會顯示出不相關的狀態。

|使用者設定狀態|預設到期日|
|:--- |:---|
| 忙碌|1 天|
| 請勿打擾|1 天|
| 其他|7 天|

> [!NOTE]
> 使用者也可以為其目前狀態手動設定持續時間。 例如，使用者可以將自己設定為 [顯示為離線] 直至明天早上。

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>比較商務用 Skype 與 Teams 中的管理設定

下列的商務用 Skype 管理設定與 Teams 不同：

- 在 Teams 中，除非啟用隱私權模式，否則組織中的使用者一律會啟用目前狀態分享。 在隱私權模式中，外部使用者無法看到目前狀態。
- Teams 中的使用者一律啟用與所有人 (包括同盟服務) 共用目前狀態。 他們的連絡人清單 (如果他們在商務用 Skype 中有此清單) 會顯示在 [聊天] > [連絡人] 底下或在 [通話] > [連絡人] 底下。
- Teams 中的使用者一律啟用用戶端的「請勿打擾」和「突破」功能。
- 當 Teams 與 Outlook 整合時，一律為使用者啟用行事曆 (包括外出和其他行事曆資訊) 整合。
- 如果組織也使用商務用 Skype，Teams 中的使用者一律啟用 [上次看到] 或 [離開時間]。

> [!NOTE]
> 目前不支援 Teams 系統管理員自訂這些設定的功能。

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>比較 Microsoft Outlook 與 Teams 中的管理設定

針對相同組織中的聯絡人，Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。

如果使用者帳戶的升級模式原則設定為 TeamsOnly，則 Outlook 會與 Teams 交談以取得目前狀態。 如果使用者帳戶未設定為 TeamsOnly，則 Outlook 會與商務用 Skype 交談。

## <a name="coexistence-with-skype-for-business"></a>與商務用 Skype 共存

請參閱[與商務用 Skype 共存](coexistence-chat-calls-presence.md)，以取得貴組織使用商務用 Skype 時 Teams的運作方式詳細資料。
