---
title: 在應用程式中管理 Bookings Microsoft Teams
author: dmaguire
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: 瞭解如何在組織中Teams中管理 Bookings 應用程式。
ms.openlocfilehash: 2bbc671b1054cfa4340abf7656e17939d147dea2
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288341"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>在應用程式中管理 Bookings Microsoft Teams

Microsoft Teams 中的 Bookings 應用程式提供一種簡單的方式，可預約面對面及虛擬會面，例如醫療保健看診、財務諮詢、面試、客戶支援、教育處室時間等等。 若要深入瞭解，請參閱使用 Teams[和 Bookings 應用程式進行虛擬訪問](expand-teams-across-your-org/bookings-virtual-visits.md)。

排程器可以從單一體驗管理多個部門與員工行事曆，以及與內部和外部出席者之間的通訊。 虛擬約會本身會透過會議Microsoft Teams，提供強大的視訊會議功能。

> [!NOTE]
> 只有排程器需要在 Teams 中安裝 Bookings 應用程式。 進行或參與虛擬約會的員工不需要應用程式。 他們只要從自己的Outlook或Teams，或從Teams確認電子郵件中的會議連結加入約會。

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>在 Teams 中使用 Bookings 應用程式的必要條件

- Exchange 信箱必須位在 Exchange Online 中。 不支援內部Exchange Server信箱。

- 必須為組織開啟 Microsoft Bookings。

- 使用者必須擁有適當的授權。 Office 365 A3、A5、E3、E5、F1、F3、Microsoft 365 A3、A5、E3、E5、F1、F3 及商務標準。

- Bookings App 的所有使用者以及所有參與會議的員工都必須擁有支援會議排程Teams授權。

- 您的系統必須符合所有[軟體與瀏覽器必要條件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams 中的 Bookings 可用性

適用于 microsoft Bookings Teams應用程式可在桌面和網頁上使用。 您可以在系統 [管理中心Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link)中的應用程式及管理應用程式Teams找到。****

### <a name="control-access-to-bookings-within-your-organization"></a>控制貴組織中 Bookings 的存取權

有幾種方法可控制能存取 Bookings 應用程式及應用程式特定功能的人員。

若要瞭解如何在 Microsoft 365 系統管理中心 中開啟或關閉 Microsoft Bookings，以及如何建立 Bookings 應用程式政策以允許選取的使用者建立 Bookings 日曆，請參閱取得[Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)的存取權。

您也可以建立[應用程式設定Teams，為](teams-app-setup-policies.md)選取的使用者釘選 Bookings 應用程式。

## <a name="recommended-meeting-policy-settings"></a>建議的會議策略設定

若要為 Bookings 提供最佳體驗，請建立Teams會議政策，以自動准許貴組織中所有人，並將該政策指派給員工。 這麼做可讓教職員自動加入約會，並啟用外部出席者大廳體驗。 深入瞭解如何自動 [允許人員參加會議](meeting-policies-participants-and-guests.md#automatically-admit-people)。

## <a name="optional-staff-approvals-setting"></a>選擇性員工核准設定

作為額外的隱私權設定，您可以選擇員工得先加入後，才能透過 Bookings 分享其排程可用性資訊，以及預約會面。  

若要啟用此設定，請前往Microsoft 365 系統管理中心 **設定** \> **設定** \> ，然後選取 **Bookings**。****

開啟此設定後，教職員會收到一封電子郵件，要求他們核准預訂日曆的成員資格。  

這項功能正逐步向全球 Microsoft 365 和 Office 365 客戶推出。 如果環境中尚未提供所有選項，請儘快回來查看。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>在設定 Bookings 信箱時變更您的預設網域

設定 Bookings 信箱時，系統會使用 Microsoft 365 或 Office 365 組織的預設電子郵件網域。 不過，這可能會導致將會議邀請傳送給外部收件者時發生問題；您的邀請可能會被標為垃圾郵件，且移至收件者的垃圾郵件資料夾，因此收件者可能永遠不會看到您的邀請。

建議您先變更預設網域，再建立 Bookings 信箱。 如需了解如何執行這項功能，請參閱[網域常見問題](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。

如果您在 Bookings 信箱建立之後需要變更預設網域，您可以使用 PowerShell 執行此作業：

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

如需詳細資訊，請參閱 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) Cmdlet 的 PowerShell 文件。

> [!NOTE]
> 如果您使用的是混合式Exchange，建議您在變更預設網域時，徹底測試內部部署Exchange與Exchange Online之間的郵件流程。

## <a name="sending-feedback"></a>傳送意見反應

歡迎您提供寶貴的意見：

  - 使用者體驗或便於使用
  - 功能差距或功能遺失
  - Bug 或問題
  
若要傳送意見回饋，請選取左導Teams底部的説明按鈕，然後選取報告所有 **問題的問題。**  在意見回饋報告開頭指出您傳送有關「Bookings」的意見回饋，以便我們輕鬆找出 Bookings 問題。

## <a name="related-articles"></a>相關文章

[管理在行動瀏覽器上Teams虛擬流覽的加入體驗](expand-teams-across-your-org/mobile-browser-join.md)


  [適用於終端使用者的 Bookings 文件](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
