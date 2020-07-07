---
title: 在 Outlook 中使用 Microsoft Teams 會議增益集
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 會在 Outlook 中安裝增益集，讓使用者從 Outlook 安排小組會議。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 877ebf8041b52e6522dc55a053e0465d4aa6a48d
ms.sourcegitcommit: ac36d3923095a4321dad14fdf23c98358affd10c
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049410"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>在 Outlook 中使用 Teams 會議增益集
=======================================

Teams 會議增益集可讓使用者從 Outlook 安排 Teams 會議。 您可以在 Windows、Mac、Web 和行動裝置上使用此增益集。

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>在 Windows 版 Outlook 中使用 Teams 會議增益集

[團隊會議] 增益集會自動安裝在 Windows 電腦上安裝 Microsoft 團隊以及 Office 2013、Office 2016 或 Office 2019 的使用者。 使用者會在 Outlook 行事曆功能區上看到 Teams 會議增益集。

![Outlook 功能區上的 Teams 會議增益集螢幕擷取畫面](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - 沒有連結至 [團隊] 增益集的**直接 URL** 。
> - 如果您的組織同時執行 [團隊] 和 [商務用 Skype]，也會有其他的考慮。 在某些情況下，Outlook 中不提供 [團隊] 增益集。 如需詳細資訊，請參閱[從商務用 Skype 升級至小組](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)。
> - 若要在電腦上安裝 Teams 會議增益集，使用者必須具備執行 Regsvr32 .exe 檔案的權限。
> - 如果使用者沒有看到 Teams 會議增益集，請指示他們關閉 Outlook 和 Teams，然後重新啟動 Teams 用戶端並登入 Teams，接著重新啟動 Outlook 用戶端 (須遵循特定順序)。
> - 如果您使用的是 Microsoft Store 提供的 Office Outlook 安裝，則不支援 Teams 會議增益集。 針對需要此增益集的使用者，建議您安裝隨選即用的 Office，如 [Windows 10 S 模式上的 Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f)一文中所述。

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>在 Mac 版 Outlook 中使用 Teams 會議增益集

Outlook for Mac 中的 [小組會議] 按鈕會顯示在 outlook for Mac 功能區中（如果 Outlook 執行的是「生產」組建16.24.414.0 及更新版本），且是使用 Microsoft 365 或 Office 365 用戶端訂閱啟動。

當使用者按一下 [傳送]**** 之後，會議座標 (Teams 的加入連結和撥入號碼) 將會新增至會議邀請。  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>在 Outlook Web App 中使用 Teams 會議增益集

如果使用者使用最新 Outlook 網頁版的早期版本，則 Outlook Web App 中的 Teams 會議按鈕將會在建立新事件時顯示。 請參閱 [Outlook 部落格](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)，了解使用者如何試用最新 Outlook 網頁版的早期版本。

![Outlook Web App 中 Teams 會議增益集的螢幕擷取畫面](media/teams-meeting-add-in-web.png)

當使用者按一下 [傳送]**** 之後，會議座標 (Teams 的加入連結和撥入號碼) 將會新增至會議邀請。  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Outlook Mobile (iOS 和 Android) 中的 Teams 會議增益集

Teams 會議按鈕會顯示在 Outlook iOS 和 Android 應用程式的最新組建中。

![Outlook Mobile 中 Teams 會議增益集的螢幕擷取畫面](media/teams-meeting-add-in-mobile.png)

當使用者按一下 [傳送]**** 之後，會議座標 (Teams 的加入連結和撥入號碼) 將會新增至會議邀請。  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a>Outlook 的團隊會議增益集與 FindTime

FindTime 是 Outlook 的增益集，可協助使用者在整個公司的會議時間達成共識。 當會議受邀者提供其偏好的時間後，FindTime 就會代表使用者傳送會議邀請。 如果 FindTime 中已選取 [線上會議]**** 選項，則 FindTime 會安排商務用 Skype 或 Microsoft Teams 會議。 (FindTime 會使用由您組織設定的任何項目作為預設的線上會議頻道)。

> [!NOTE]  
> 如果您已在 [FindTime 儀表板](https://findtime.microsoft.com/UserDashboard)中儲存商務用 Skype 的設定，FindTime 就會使用該設定，而不是使用 Microsoft Teams。 如果您想要使用 Microsoft Teams，請刪除儀表板中的商務用 Skype 設定。

如需詳細資訊，請參閱[使用 FindTime 排程會議](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)。

## <a name="authentication-requirements"></a>驗證需求

Teams 會議增益集需要使用者使用新式驗證來登入 Teams。 如果使用者不使用此方法登入，他們仍能使用團隊用戶端，但無法使用 Outlook 增益集來排程小組線上會議。 若要修正此問題，請執行下列其中一項操作：

- 如果您的組織未設定新式驗證，則您應設定新式驗證。
- 如果已設定新式驗證，但在對話方塊中將其取消，您應指示使用者使用多重要素驗證再次登入。

若要深入了解如何設定驗證，請參閱 [Microsoft Teams 中的身分識別模型與驗證](identify-models-authentication.md)。

## <a name="enable-private-meetings"></a>啟用私人會議

必須在 Microsoft Teams 系統管理中心啟用 [允許私人會議排程]****，才能部署此增益集。 在系統管理中心中，移至 [會議]**** > [會議原則]****，並在 [一般]**** 區段中，將 [允許私人會議排程]**** 切換為 [開啟]。

![Microsoft Teams 系統管理中心的設定螢幕擷取畫面。](media/teams-add-in-for-outlook-image1.png)

Teams 用戶端會藉由判斷使用者需要 32 位元或 64 位元版本，來安裝正確的增益集。

> [!NOTE]
> 在安裝或升級 Teams 之後，使用者可能需要重新啟動 Outlook，才能取得最新的增益集。

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Teams 升級原則和適用於 Outlook 的 Teams 會議增益集

客戶可以[選擇從商務用 Skype 升級到 Teams 的作業過程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)。 租用戶系統管理員可以使用 Teams 共存模式來為使用者定義此過程。 租用戶系統管理員可以選擇讓使用者並行使用 Teams 和商務用 Skype (離島模式)。 

當使用離島模式的使用者在 Outlook 中安排會議時，他們通常能夠選擇要安排商務用 Skype 或 Teams 會議。 在 Outlook 網頁版、Outlook Windows 版和 Outlook Mac 版中，使用者會在預設使用孤島模式時，看到 [商務用 Skype] 和 [團隊] 增益集。 您可以設定 [團隊會議原則] 設定來控制 [孤島] 模式中的使用者只能使用 [團隊會議] 增益集，或是同時使用 [團隊會議] 和 [商務用 Skype 會議] 增益集。

由於初次發行時的特定限制，Outlook Mobile 只能支援建立商務用 Skype **或** Teams 會議。 請參閱下列資料表以取得詳細資料。

| Teams 系統管理中心的共存模式 | Outlook Mobile 中的預設會議提供者 |
| --------------------------------------|---------------------------------------------|
| 離島 | 商務用 Skype |
| 僅商務用 Skype | 商務用 Skype |
| 商務用 Skype 搭配 Teams 共同作業 | 商務用 Skype |
| 商務用 Skype 搭配 Teams 共同作業和會議 | Teams |
| 僅 Teams | Teams |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a>設定 [孤島] 模式中的使用者是否只能使用 [團隊會議] 增益集，或同時使用團隊會議增益集及商務用 Skype 會議增益集

身為系統管理員，您可以設定團隊會議原則設定，以控制將哪個 Outlook 會議增益集用於使用*孤島模式的使用者*。 您可以指定使用者是否只能使用 [團隊會議] 增益集，或是同時使用 [團隊會議] 和 [商務用 Skype 會議] 增益集，在 Outlook 中排程會議。

您只能將此原則套用到使用孤島模式的使用者，並在其團隊會議原則中，將**AllowOutlookAddIn**參數設定為**True** 。 如需如何設定此原則的步驟，請參閱以[孤島模式為使用者設定會議提供者](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)。

## <a name="other-considerations"></a>其他考量事項

Teams 會議增益集是仍在建置的功能，因此請注意下列事項：

- 此增益集適用於具有特定參與者的排程會議 (不適用於頻道中的會議)。 頻道會議必須從 Teams 內排程。
- 如果驗證 Proxy 位於使用者電腦和團隊服務的網路路徑中，增益集將無法運作。
- 使用者無法從 Outlook 中安排即時活動。 請移至 Teams 以安排即時活動。 如需詳細資訊，請參閱[什麼是 Microsoft Teams 即時活動？](teams-live-events/what-are-teams-live-events.md)。

深入了解 [Microsoft Teams 中的會議和通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。

## <a name="troubleshooting"></a>疑難排解

使用下列步驟來疑難排解團隊會議增益集的相關問題。

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a>Windows 版 Outlook 中的 [團隊會議增益集] 不會顯示

如果您無法取得適用於 Outlook 的 Teams 會議增益集，請嘗試這些疑難排解步驟。

[下載](https://aka.ms/SaRA-TeamsAddInScenario)並執行[Microsoft 支援修復](https://aka.ms/SaRA_Home)小幫手，以執行自動疑難排解步驟和修正程式。

或者，您也可以手動執行下列步驟：

- Windows 7 使用者必須[在 Windows 中安裝通用 C 運行](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)時間的更新，小組會議增益集才能運作。
- 確認使用者擁有小組升級原則，可在小組中排程會議。 如需詳細資訊，請參閱[從商務用 Skype 升級至團隊](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)。
- 確認使用者擁有允許 Outlook 增益集的小組會議原則。 如需詳細資訊，請參閱[在團隊中管理會議原則](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in)。
- 確定使用者已安裝 [團隊桌面用戶端]。 只有使用團隊網頁用戶端時，才能安裝會議增益集。
- 確定使用者已安裝 Outlook 2013 或更新版本。
- 確認使用者擁有執行 regsvr32.exe 的許可權。
- 確認已套用所有適用于 Outlook 桌面用戶端的更新。
- 請遵循下列步驟：
  - 重新啟動 Teams 桌面版用戶端。
  - 登出 Teams 桌面用戶端，然後重新登入。
  - 重新啟動 Outlook 桌面用戶端。 （請確定 Outlook 未在系統管理員模式下執行）。

如果您仍然沒有看到增益集，請確認它沒有在 Outlook 中停用。

- 在 Outlook 中，**選擇 [檔案]，然後**選擇 [**選項**]。
- 選取 [ **Outlook 選項**] 對話方塊的 [**增益集**] 索引標籤。
- 確認 microsoft **Office 的 Microsoft 團隊會議載入**宏已列于 [作用中的**應用程式增益集**] 清單中
- 如果 [團隊會議] 增益集列于 [**停用的應用程式增益集**] 清單中，請選取 [**管理**] 中**的 [COM 增益集**]，然後選取 [執行 **...** ]。
- 在**Microsoft Office 的 [Microsoft 團隊會議增益集**] 旁，設定核取方塊。
- 在所有對話方塊中選擇 **[確定]** ，然後重新開機 Outlook。

如需有關如何管理增益集的一般指導方針，請參閱[在 Office 程式中查看、管理及安裝增益集](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。

如果該增益集仍未顯示，請使用下列步驟驗證登錄設定。

> [!NOTE]
> 不正確地編輯註冊表可能會嚴重損壞您的系統。 在變更註冊表之前，您應該先備份電腦上任何有價值的資料。
- 啟動 RegEdit.exe
- 流覽至 HKEY_CURRENT_USER \Software\Microsoft\Office\Outlook\Addins
- 確認 TeamsAddin 已存在。
- 在 TeamsAddin 中，確認 LoadBehavior 存在並設定為3。
  - 如果 LoadBehavior 的值不是3，請將它變更為3，然後重新開機 Outlook。

### <a name="delegate-scheduling-does-not-work"></a>代理人排程無法運作

如果您的系統管理員已將 Microsoft Exchange 設定為[控制對 Exchange Web 服務器 (EWS) 的存取](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)，代理人將無法代表老闆安排 Teams 會議。 此設定的解決方案正在開發中，即將在未來發行。 作為因應措施，您的系統管理員可以將下列字串新增至 EWS 允許清單： "*SchedulingService*"。 


