---
title: 在 Microsoft Teams 中管理Bookings應用程式
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
description: 瞭解如何在Teams中為組織中的使用者管理Bookings應用程式。
ms.openlocfilehash: aab7ce7a4813d851574f9a5796f5ce21d44774ff
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853064"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>在 Microsoft Teams 中管理Bookings應用程式

Microsoft Teams中的 Bookings 應用程式提供簡單的親自和虛擬約會排程方式。 例如，醫療探訪、財務諮詢、面談、客戶支援，以及教育辦公室時間。 若要深入瞭解，請參閱[使用Teams的虛擬約會和Bookings應用程式](expand-teams-across-your-org/bookings-virtual-visits.md)。

排程器可以從單一體驗管理多個部門和教職員行事曆，以及與內部和外部出席者通訊。 虛擬約會會透過Microsoft Teams會議進行，以提供強大的視訊會議功能。

> [!NOTE]
> 只有排程器需要在 Teams 中安裝 Bookings 應用程式。 進行虛擬約會或參與虛擬約會的員工不需要此應用程式。 他們可以直接從Outlook或行事曆Teams加入約會，或從預約確認電子郵件中的Teams會議連結加入約會。

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>在 Teams 中使用 Bookings 應用程式的必要條件

* Exchange信箱位於Exchange Online中。 不支援內部部署Exchange Server信箱。
* Microsoft Bookings適用于組織。
* 使用者有適當的授權。 Office 365 A3、A5、E3、E5、F1、F3、Microsoft 365 A3、A5、E3、E5、F1、F3 和商務標準都受到支援。
* Bookings應用程式的所有使用者和參與會議的所有教職員都擁有支援Teams會議排程的授權。
* [軟體和瀏覽器必要條件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams 中的 Bookings 可用性

適用于Teams的Microsoft Bookings應用程式可在桌面和網頁上使用。 您可以 [在 [Teams 中的應用程式](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link)] 底下，以及在 [管理Teams系統管理中心的 [**管理應用程式**] 底下找到。

### <a name="control-access-to-bookings-within-your-organization"></a>控制貴組織中 Bookings 的存取權

有幾種方法可控制能存取 Bookings 應用程式及應用程式特定功能的人員。 您可以讓Microsoft Bookings應用程式可用，或停用Microsoft 365 系統管理中心。 或者，您可以建立Bookings應用程式原則，允許選取的使用者建立Bookings行事曆。 請參閱[存取Microsoft Bookings](/microsoft-365/bookings/get-access)。

您也可以[建立Teams應用程式設定原則，為特定使用者釘選Bookings應用程式](teams-app-setup-policies.md)。

## <a name="recommended-meeting-policy-settings"></a>建議的會議原則設定

若要為Bookings提供最佳體驗，請建立Teams會議原則，自動允許 **貴組織中的所有人**，並將原則指派給您的員工。 此原則可讓員工自動加入約會，並為外部出席者啟用大廳體驗。 瞭解 [如何自動允許人員加入會議](meeting-policies-participants-and-guests.md#automatically-admit-people)。

## <a name="optional-staff-approvals-setting"></a>選擇性員工核准設定

您可以要求員工先加入，然後Bookings分享其排程可用性資訊，然後其他人才能與他們排程約會。

若要啟用此設定，請移至 **Microsoft 365 系統管理中心 設定** \>  \> **設定**，然後選 **取 [Bookings]**。

開啟此設定後，教職員會收到一封電子郵件，要求他們核准預約行事曆的成員資格。  

這項功能正逐步向全球 Microsoft 365 和 Office 365 客戶推出。 如果您的環境中尚未提供所有選項，請儘快回來查看。

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>設定信箱時變更預設網域Bookings

設定 Bookings 信箱時，系統會使用 Microsoft 365 或 Office 365 組織的預設電子郵件網域。 不過，預設網域可能會在傳送會議邀請給外部收件者時造成問題。 例如，您的邀請可能會被標幟為垃圾郵件，並移至收件者的垃圾郵件資料夾，因此收件者可能永遠不會看到您的邀請。

建議您先變更預設網域，再建立Bookings信箱。 請參閱 [網域常見問題](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。

如果您在建立Bookings信箱之後需要變更預設網域，請使用 PowerShell。

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

請參閱設定 [信箱](/powershell/module/exchange/mailboxes/set-mailbox) Cmdlet 的 PowerShell 檔。

> [!NOTE]
> 如果您使用的是Exchange混合式設定，建議您在變更預設網域時，徹底測試內部部署Exchange與Exchange Online之間的郵件流程。

## <a name="send-feedback"></a>傳送意見反應

歡迎您提供寶貴的意見：

* 使用者體驗或便於使用
* 功能差距或功能遺失
* Bug 或問題
  
若要傳送意見反應，請選取左Teams導覽列底部的 **[說明]** 選項，然後選取 [**回報****所有** 問題的問題]。 在意見反應報告的開頭表示您要傳送有關「Bookings」的意見反應，讓我們可以輕鬆找出Bookings問題。

## <a name="related-articles"></a>相關文章

[在瀏覽器上管理Teams虛擬約會的加入體驗](expand-teams-across-your-org/browser-join.md)


  [適用於終端使用者的 Bookings 文件](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
