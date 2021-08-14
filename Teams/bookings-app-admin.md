---
title: 使用 Microsoft Teams 和 Bookings 應用程式進行虛擬會面
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: 使用 Bookings 應用程式進行 Microsoft Teams 和虛擬會面
ms.openlocfilehash: 2ef4708cfcbdda5ba55c1aa7069e6e1e6babebc2
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233398"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>使用 Microsoft Teams 和 Bookings 應用程式進行虛擬會面

Microsoft Teams 中的 Bookings 應用程式提供一種簡單的方式，可預約面對面及虛擬會面，例如醫療保健看診、財務諮詢、面試、客戶支援、教育處室時間等等。

排程器可以從單一體驗管理多個部門與員工行事曆，以及與內部和外部出席者之間的通訊。 虛擬會面本身透過 Microsoft Teams 會議進行，提供強大的會議功能。

> [!NOTE]
> 只有排程器需要在 Teams 中安裝 Bookings 應用程式。 進行或參與虛擬會面的員工不需要應用程式。 他們只需透過 Outlook 或 Teams 行事曆，或是預約確認電子郵件中的連結即可加入會面。

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>在 Teams 中使用 Bookings 應用程式的必要條件

- Exchange 信箱必須位在 Exchange Online 中。 不支援內部部署 Exchange Server 信箱。

- 必須為組織開啟 Microsoft Bookings。

- 使用者必須擁有適當的授權。 Office 365 A3、A5、E3、E5、F1、F3、Microsoft 365 A3、A5、E3 和 E5、商務標準版。

- Bookings 應用程式的所有使用者，以及所有參與會議的員工都必須擁有支援 Teams 會議排程授權。

- 您的系統必須符合所有[軟體與瀏覽器必要條件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams 中的 Bookings 可用性

適用於 Teams 的 Microsoft Bookings 應用程式可在桌面和 Web 上使用。 您可以在 [Microsoft Teams 中的 應用程式](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 下，以及 Teams 系統管理中心的 **管理應用程式** 下找到。

### <a name="control-access-to-bookings-within-your-organization"></a>控制貴組織中 Bookings 的存取權

有幾種方法可控制能存取 Bookings 應用程式及應用程式特定功能的人員。 如需了解如何在 Microsoft 365 系統管理中心開啟或關閉 Microsoft Bookings，以及如何建立 Bookings 應用程式原則以讓選取的使用者建立 Bookings 行事曆，請參閱[取得 Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)。 您也可以了解如何[建立 Teams 應用程式原則，以釘選特定使用者的 Bookings 應用程式](teams-app-setup-policies.md)。

## <a name="recommended-meeting-policy-settings"></a>建議的會議原則設定

如需為 Bookings 啟用最佳體驗，請建立人員會議原則，以自動准許 **您組織的中所有人**。 這可讓員工自動加入會面，並啟用外部出席者的大廳體驗。 您可以深入了解如何[自動准許人員參加會議](meeting-policies-participants-and-guests.md#automatically-admit-people)。

### <a name="optional-staff-approvals-setting"></a>選擇性員工核准設定

作為額外的隱私權設定，您可以選擇員工得先加入後，才能透過 Bookings 分享其排程可用性資訊，以及預約會面。  

如需啟用此設定，請前往 **Microsoft 365 系統管理中心** \> **設定** \> **設定**，然後選取 **Bookings**。

開啟此設定後，員工會收到一封電子郵件，要求他們核准預約行事曆的成員資格。  

這項功能正逐步向全球 Microsoft 365 和 Office 365 客戶推出。 如果環境中尚未提供所有選項，請之後再返回查看。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>在設定 Bookings 信箱時變更您的預設網域

設定 Bookings 信箱時，系統會使用 Microsoft 365 或 Office 365 組織的預設電子郵件網域。 不過，這可能會導致將會議邀請傳送給外部收件者時發生問題；您的邀請可能會被標為垃圾郵件，且移至收件者的垃圾郵件資料夾，因此收件者可能永遠不會看到您的邀請。

建議您在建立 Bookings 信箱之前先變更預設網域。 如需了解如何執行這項功能，請參閱[網域常見問題](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。

如果您在 Bookings 信箱建立之後需要變更預設網域，您可以使用 PowerShell 執行此作業：

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

如需詳細資訊，請參閱 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) Cmdlet 的 PowerShell 文件。

> [!NOTE]
> 如果您使用 Exchange 混合式原則，建議您在變更預設網域時，徹底測試內部部署 Exchange 和 Exchange Online 之間的郵件流程。

## <a name="sending-feedback"></a>傳送意見反應

歡迎您提供寶貴的意見：

  - 使用者體驗或便於使用
  - 功能差距或功能遺失
  - Bug 或問題
  
如需傳送意見，請按一下 Teams 左側瀏覽列底部附近的 **[說明]** 按鈕，然後針對 **[所有]** 問題按一下 **[回報問題]**。 請在您的意見反應報告開頭處標註，您傳送的是有關「Bookings」的意見，以便我們識別 Bookings 問題。

## <a name="related-topics"></a>相關主題


  [適用於終端使用者的 Bookings 文件](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)