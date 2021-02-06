---
title: 使用 Microsoft 團隊和預定 app 進行虛擬走訪
author: msdmaguire
ms.author: dmaguire
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
description: 使用預訂 App 進行 Microsoft 團隊和虛擬走訪
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125746"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>使用 Microsoft 團隊和預定 app 進行虛擬走訪

Microsoft 團隊中的 [預定] 應用程式提供一種簡單的方式來排程人員與虛擬約會，例如醫療保健走訪、財務諮詢、訪談、客戶支援、教育 office 時間等。

計畫者可以管理多個部門和員工行事曆，以及從單一體驗中與內部及外部出席者進行通訊。 虛擬約會本身會透過 Microsoft 團隊會議進行舉行，提供強健的視訊會議功能。

> [!NOTE]
> 只有計畫者需要在小組中安裝預定 app。 員工進行或參與虛擬約會不需要 app。 他們可以直接從他們的 Outlook 或團隊行事曆，或從其預訂確認電子郵件中的連結加入約會。

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>在團隊中使用預定 app 的先決條件

- Exchange 信箱必須位於 Exchange Online 中。 不支援內部部署 Exchange Server 信箱。

- 您必須為組織開啟 Microsoft 預訂。

- 使用者必須具備適當的授權。 支援 Office 365 A3、A5、E3 和 E5，以及 Microsoft 365 商務標準、A3、A5、E3 和 E5。

- 預訂 app 的所有使用者以及參與會議的所有人員都必須擁有支援小組會議排程的授權。

- 您的系統必須符合所有 [軟體和瀏覽器的先決條件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>團隊中的預訂可用性

您可以在桌面和 web 上取得適用于團隊的 Microsoft 預訂 App。 它可以在 [Microsoft 團隊內](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 的 [應用程式] 底下，在 [管理團隊內的 **App** ] 系統管理中心找到。

### <a name="control-access-to-bookings-within-your-organization"></a>控制貴組織內的預訂存取權

有幾種方式可以控制誰有權存取預訂 app，以及應用程式的特定功能。 若要瞭解如何在 Microsoft 365 系統管理中心開啟或關閉 Microsoft 預訂，以及如何建立預訂 app 原則，以允許選取的使用者建立預定行事曆，請參閱 [取得 Microsoft 預訂的存取權](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)。 您也可以瞭解如何 [建立團隊 app 原則，以釘選使用者的預訂 app](teams-app-setup-policies.md)。

## <a name="recommended-meeting-policy-settings"></a>建議的會議原則設定

若要為預訂提供最佳的使用體驗，請建立員工會議原則來自動承認 **貴組織中的每個人**。 這可讓員工自動加入約會，並啟用外部出席者的會議廳體驗。 您可以深入瞭解如何 [將人員自動 admitting 到會議](meeting-policies-in-teams.md#automatically-admit-people)。

### <a name="optional-staff-approvals-setting"></a>選用員工核准設定

如果您是額外的隱私權設定，您可以選擇 [要求員工在排程的可用性資訊透過預訂共用之後，且可在預訂約會前進行選擇。  

若要啟用此設定，請移至 **Microsoft 365 系統管理中心** \> **設定** \> **設定**，然後選取 [ **預定**]。

開啟此設定時，員工將會收到一封電子郵件，要求他們在其中向預定行事曆核准成員資格。  

這項功能在全球範圍內逐漸推出給 Microsoft 365 和 Office 365 客戶。 如果您的環境中尚未提供所有選項，請稍後再查看。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>在設定預訂信箱時變更您的預設網域

在設定預訂信箱時，會使用您的 Microsoft 365 或 Office 365 組織的預設電子郵件網域。 不過，這可能會在傳送會議邀請給外部收件者時發生問題;您的邀請可能會標示為垃圾郵件，並移至收件者的 [垃圾郵件] 資料夾，所以收件者可能不會看到您的邀請。

建議您先變更預設網域，然後再建立您的預定信箱。 如需如何執行此動作的詳細資訊，請參閱 [網域常見問題](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。

如果您在已建立預定信箱後需要變更預設網域，您可以使用 PowerShell 進行下列操作：

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

如需詳細資訊，請參閱 [設定信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) Cmdlet 的 PowerShell 檔。

> [!NOTE]
> 如果您使用的是 Exchange 混合式設定，我們建議您在變更預設網域時，在內部部署 Exchange 和 Exchange Online 之間徹底測試郵件流程。

## <a name="sending-feedback"></a>傳送意見反應

我們歡迎您提供意見反應：

  - 使用者體驗或易用性
  - 功能缺口或遺失的功能
  - 錯誤或問題
  
若要傳送意見反應，請 **按一下位於小組** 左側導覽列附近的 [說明] 按鈕，然後按一下 [針對 **所有** 問題 **報告問題**]。 請注意，您要傳送意見反應給您的意見反應報告開始，您會收到「預定」的意見反應，讓我們可以輕鬆找出預訂問題。

## <a name="related-topics"></a>相關主題

[最終使用者的預定檔](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
