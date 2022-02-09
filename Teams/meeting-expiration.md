---
title: 會議政策與會議到期Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: 瞭解如何使用會議策略設定來控制會議Microsoft Teams。
ms.openlocfilehash: 8c8a5603aea6ac65a2cd35b12eca9250debc7c51
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279170"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>會議政策與會議到期Microsoft Teams

[會議Microsoft Teams](meeting-policies-overview.md)用來控制貴組織中使用者是否可以開始和排程會議，以及會議參與者對於使用者排程的會議可用的功能。 您可以使用全域 (全組織預設值) 原則，或建立並指派自訂原則。 您可以在系統管理中心Microsoft Teams使用 Get、[New](/powershell/module/skype/new-csteamsmeetingpolicy)、[Set](/powershell/module/skype/set-csteamsmeetingpolicy)、[Remove](/powershell/module/skype/remove-csteamsmeetingpolicy)、[Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell Cmdlet 來管理會議策略。[ ](/powershell/module/skype/get-csteamsmeetingpolicy)

控制使用者是否可以開始和排程會議，以及控制使用者排程的會議到期的會議策略設定。 當會議加入連結和會議 ID 到期時，沒有人可以加入會議。 下列會議策略設定會決定使用者是否可以在 Teams 中開始和排程Teams。 本文討論會議設定。

- [現在在頻道中開會](meeting-policies-in-teams-general.md#meet-now-in-channels)：控制使用者是否可以在頻道中啟動即席會議。
- [頻道會議排程](meeting-policies-in-teams-general.md#channel-meeting-scheduling)：控制使用者是否可以在頻道中排程會議。
- [私人會議排程](meeting-policies-in-teams-general.md#private-meeting-scheduling)：控制使用者是否可以在 Teams。 當會議未發佈到小組中的頻道時，會議是私人的。
- [Outlook：](meeting-policies-in-teams-general.md#outlook-add-in)控制使用者是否可以從 Outlook 排程私人Outlook。 當會議未發佈到小組中的頻道時，會議是私人的。
- [現在在私人會議中開會](meeting-policies-in-teams-general.md#meet-now-in-private-meetings)：控制使用者是否可以啟動即席私人會議。

根據預設，這些設定為啟用狀態。 當其中任一設定關閉時，指派該策略的任何使用者都無法開始或排程該類型的新會議。 同時，使用者先前啟動或排定到期之所有類型之會議的會議加入連結和會議 ID。

例如，如果使用者已指派會議策略，其中這些會議策略設定設定為 **開啟**，然後您關閉頻道中的立即開會設定，該使用者便無法再在頻道中啟動即席會議，而使用者先前建立的會議現在加入連結的頻道已過期。 使用者仍然可以開始和排程其他會議類型，並加入由其他人組織的會議。

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>當會議加入連結和會議 ID 到期時，會發生什麼情況？

當會議加入連結和會議 ID 到期時，沒有人可以加入會議。 當使用者嘗試透過連結或電話加入會議時，會收到一則訊息，指出會議已不再提供。 交談、檔案、白板、錄製、文字記錄及其他與會議相關的內容會保留，使用者仍然可以存取這些內容。

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>當您開啟並關閉會議策略設定時，會發生什麼情況？

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>將會議策略設定從開啟切換為關閉

當會議策略設定設為 **On** 時，指派該策略的使用者可以開始或排程該類型的會議，而且每個人都可以加入。 當您將會議策略設定切換為 **關閉** 時，指派該策略的使用者無法開始或排程該類型的新會議，而且使用者先前排程的現有會議的會議加入連結和會議 ID 已過期。

請記住，使用者仍然可以加入由其他人組織的會議。

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>將會議策略設定從關閉切換到開啟

當您將會議策略設定從 **關閉** 切換到 **開啟** 時，指派該策略的使用者可以開始或排程該類型的會議。 如果會議策略設定已關閉，然後使用者再次開啟，則使用者組織的所有先前排定的 (和過期的) 會議都變成使用中，而使用者可以使用會議加入連結或電話加入會議。  

## <a name="meeting-expiration-scenarios"></a>會議到期案例

以下摘要說明會議到期對於本文中討論之每一個會議政策設定如何運作。

|如果您想要...&nbsp;&nbsp; |執行此&nbsp;&nbsp;&nbsp;&nbsp;  |會議加入行為&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|到期私人會議現在由使用者啟動的會議&nbsp;&nbsp;|在私人 **會議中關閉現在開會**。&nbsp;&nbsp;|現在沒有人可以 **加入由使用者** 啟動的私密會議。|
|將使用者排程的私人會議到期&nbsp;&nbsp;|關閉 **私人會議排程**_，並_ 關閉 **Outlook附加元件**。 &nbsp;&nbsp;|沒有人可以加入使用者排程的私人會議。 這可防止人員加入下列會議：<ul><li>過去發生的私人會議。</li><li>已排程為未來的私人會議，但尚未進行。</li><li>未來週期性私人會議的實例。</li></ul><br>私人 **會議排程** 和 **Outlook** 都必須關閉，使用者排程的私人會議必須到期。 如果其中一個設定已關閉，另一個設定為已啟用，則現有會議的會議加入連結和會議 ID 會維持為使用中狀態，且不會過期。|
|頻道到期 **會議現在** 由使用者啟動的會議&nbsp;&nbsp;|關閉頻道 **中的現在開會**_，並_ 關閉 **頻道會議排程**。&nbsp;&nbsp;|沒有人可以加入頻道 **會議現在** 由使用者啟動的會議。|
|使用者排程的頻道會議到期&nbsp;&nbsp;|關閉 **通道會議排程**。&nbsp;&nbsp;|沒有人可以加入使用者排程的頻道會議。 這可防止人員加入下列會議：<ul><li>過去發生的頻道會議。</li><li>已排程為未來的頻道會議，但尚未進行。</li><li>未來週期性頻道會議的實例。</li></ul>|

如果您希望人員存取先前由特定使用者排程或啟動的會議，您可以：

- 開啟該使用者的會議策略設定。
- 關閉該使用者的會議策略設定，讓另一個已啟用該策略設定的使用者建立新會議以取代過期的會議。

> [!NOTE]
> 如果會議是由代理人傳送，而代理人獲派代表另一個人傳送會議邀請的許可權 ，例如主管，會議原則設定會適用于授予許可權 (主管) 。

## <a name="changes-to-meeting-expiration"></a>會議到期變更

> [!IMPORTANT]
> 如果您想要在租使用者Teams啟用會議到期日，請Microsoft Teams[提早採用者計畫](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR8YMDA0A9INMv_DZ8yW5uG1URDc3U1VVMklPTzVMS0RLR0pUQTlWU1BEVC4u)。

所有新Teams TMRs (錄製) 預設到期日為 60 天。 此選項預設為所有租使用者。 這表示根據預設，開啟此功能後建立的所有 TMRs 都會在建立日期後的 60 天后刪除。 系統管理員也可以將會議設定 **為永不自動過期**。 系統OneDrive系統SharePoint所有 TMRs 上設定到期日，並會在到期日自動將 TMRs 移至回收站。

自動會議到期是一種輕量型的管家機制，可以減少舊版 TMRs 所造成儲存空間的雜亂。 平均而言，在所有客戶中，96% 的 TMRs 在 60 天后不會觀看，99% 在 110 天后不會觀看。 我們相信，移除 60 天后可能不會再觀看的錄製內容，幾乎所有客戶都會受益于租使用者降低的儲存空間負載。 根據預設，我們的目標是盡可能為所有客戶提供乾淨體驗。

使用會議到期限制OneDrive或SharePoint由會議記錄所導向的雲端Teams耗用。 一般的會議錄製會耗用每小時約 400 MB 的錄製。

> [!NOTE]
> A1 使用者的預設到期日上限為 30 天。

### <a name="expiration-date"></a>有效期

- 到期日的計算方式為建立日期，加上系統管理員在 Teams中設定 **的預設天數**。
- 播放不會影響到期日。

### <a name="change-the-default-expiration-date"></a>變更預設到期日

系統管理員可以在 PowerShell 或系統管理中心編輯Teams設定。 任何變更只會影響 *從該點* 起新建立 TMRs。 這不會影響該日期之前建立的任何錄製。 系統管理員無法變更現有 TMRs 的到期日。 這麼做是為了保護擁有 TMR 的使用者決定。 會議與通話都可以由此設定控制。

到期日值可以設定為：

- 最小值： **1 天**
- 最大值： **99，999 天**
- 您也可以將到期日設定為 **-1** ，讓錄製永不過期。

PowerShell 命令範例：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

您可以在會議Teams系統管理中心中設定 **到期日。** 開啟會議自動 **到期** 後，您就會獲得設定錄製到期的選項。

![系統管理中心會議到期政策螢幕擷取畫面。](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>安全性與合規性

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>我應該仰賴這項功能來嚴格遵循安全性與合規性嗎？

否，您不應該仰賴這項法律保護，因為使用者可以修改他們控制的任何錄製的到期日。

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>我在安全性與合規性中心所設定保留和/或刪除&是否Teams會議錄製到期日設定？

是，您設定在合規性中心的任何政策都會以完全優先。

例如：

- 如果您有一項規定，指出網站中所有檔案都必須保留 100 天，而 Teams 會議錄製的到期日設定是 30 天，則錄製內容會保留完整 100 天。
- 如果您有刪除政策，指出所有 Teams 會議錄製都會在 5 天后刪除，而且您的 Teams 會議錄製有 30 天的到期日設定，則錄製內容將在 5 天后刪除。

### <a name="will-this-feature-enforce-file-retention"></a>啟用此功能會強制執行檔案保留？

否，由於此功能及其設定，檔案不會保留。 如果具有刪除許可權的使用者嘗試刪除具有到期設定之 TMR，將會執行該使用者的刪除動作。

### <a name="what-skus-are-required-for-this-feature"></a>這項功能需要哪些 SKUs ?

- 根據預設，所有 SKU 都會有此功能。
- A1 使用者預設為最多 30 天的到期日，但他們可以變更到期日。

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>如果我想要系統管理員對會議錄製的生命週期擁有完全控制權，但不想讓使用者能夠重寫到期日，該怎麼處理？

我們建議您使用安全性與合規性保留和/或刪除政策。 提供該功能的目標是解決複雜的原則與 SLA 導向的管理法律考量。

自動過期功能僅做為輕量型管家管理機制，以減少從舊式會議錄製Teams雜亂。

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>未來在此功能釋出後, 從傳統資料流移轉來的 TMR 也將套用自動到期？

否，移轉的 TMR 不會有到期設定。 相反地，我們鼓勵系統管理員只遷移他們想要保留的 TMR。 移轉文件將會提供更多詳細資料。

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>此功能與當 TMR 上傳至 OneDrive 失敗時SharePoint不同？

當錄製無法上傳到 OneDrive 或 SharePoint 時，Teams 應用程式會在聊天中顯示一則訊息，指出使用者在從 Teams 伺服器永久刪除 TMR 之前，最多有 21 天的時間下載 TMR。 由於 TMR 上傳失敗而現有的到期體驗與說明文件中OneDrive SharePoint的自動到期功能相關。

## <a name="related-topics"></a>相關主題

[變更會議到期日 - 使用者控制項](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[管理 Teams 中的會議原則](meeting-policies-overview.md)

[將原則指派給 Teams 中的使用者](policy-assignment-overview.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)


