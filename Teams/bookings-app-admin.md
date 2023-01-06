---
title: 在 Microsoft Teams 中管理 Bookings 應用程式
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: how-to
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
- m365-frontline
- tier2
- highpri
- m365initiative-meetings
ms.reviewer: ''
description: 瞭解如何在 Teams 中為組織中的使用者管理 Bookings 應用程式。
ms.openlocfilehash: 66e3d0450eaad1843c94833cb7bb6d417959eb8c
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727755"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>在 Microsoft Teams 中管理 Bookings 應用程式

Microsoft Teams 中的 Bookings 應用程式提供一個簡單的方式來排程親自和虛擬約會。 例如，醫療探訪、財務諮詢、面談、客戶支援，以及教育辦公室時間。 若要深入瞭解，請[參閱使用 Teams 和 Bookings 應用程式虛擬約會](/microsoft-365/frontline/bookings-virtual-appointments)。

排程器可以從單一體驗管理多個部門和教職員行事曆，以及與內部和外部出席者通訊。 虛擬約會會透過 Teams 會議進行，以提供強大的視訊會議功能。

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>在 Teams 中使用 Bookings 應用程式的先決條件

* Exchange 信箱位於Exchange Online中。 不支援內部部署Exchange Server信箱。
* Microsoft Bookings適用于組織。
* 使用者有適當的授權。 Office 365 A3、A5、E1、E3、E5、F1、F3、Microsoft 365 A3、A5、E3、E5、F1、F3 和商務標準都受到支援。
* Bookings 應用程式的所有使用者和參與會議的所有員工都擁有支援 Teams 會議排程的授權。
* [軟體和瀏覽器必要條件](hardware-requirements-for-the-teams-app.md)。

## <a name="availability-of-bookings-in-teams"></a>Teams 中的 Bookings 可用性

Teams 版 Bookings 應用程式可在桌面和網頁上使用。 您可以 [在 Teams 中的應用程式](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 和 Teams 系統管理中心的 [ **管理應用程式** ] 底下找到。

## <a name="control-access-to-bookings-within-your-organization"></a>控制貴組織中 Bookings 的存取權

有幾種方法可控制能存取 Bookings 應用程式及應用程式特定功能的人員。 您可以讓Microsoft Bookings應用程式可用，或停用Microsoft 365 系統管理中心。 或者，您可以建立 Bookings 應用程式原則，允許選取的使用者建立 Bookings 行事曆。 請參閱[存取Microsoft Bookings](/microsoft-365/bookings/get-access)。

您也可以 [建立 Teams 應用程式設定原則，將 Bookings 應用程式釘選給特定使用者](teams-app-setup-policies.md)。

## <a name="recommended-meeting-policy-settings"></a>建議的會議原則設定

若要為 Bookings 啟用最佳體驗，請建立 Teams 會議原則以自動准許 **貴組織中的所有人** ，並將原則指派給您的教職員。 此原則可讓員工自動加入約會，並為外部出席者啟用大廳體驗。 瞭解 [如何自動允許人員加入會議](meeting-policies-participants-and-guests.md#automatically-admit-people)。

如需會議原則的詳細資訊，請參閱 [管理 Teams 中的會議原則](meeting-policies-in-teams.md) 、 [會議原則和 Teams 中的會議到期日](meeting-expiration.md)。

## <a name="sms-text-notifications"></a>簡訊通知

![資訊圖示 ](media/info.png) **此功能正移至 [Teams 進階版 (](teams-add-on-licensing/licensing-enhance-teams.md) Preview) 。使用者可以在預覽期間繼續使用此功能。預覽之後，使用者需要Teams 進階版授權。**

> [!NOTE]
> 我們將于 2023 年 3 月 1 日 (之前于 2023 年 1 月 31 日) 提供無限制的簡訊通知給擁有 Bookings 授權的客戶。 隨著我們即將結束促銷期間，我們將提供授權需求的其他詳細資料。 請連絡您的帳戶小組或支援，以在促銷期間之後收到價格詳細資料。

您可以控制是否可以傳送簡訊簡訊通知給外部出席者，以進行貴組織員工排程的虛擬約會。

根據預設，此設定為開啟狀態，且貴組織中所有 Bookings 行事曆都會啟用簡訊通知。 請記住，Bookings 系統管理員和排程器稍後可以選擇在 [排定的約會類型](/microsoft-365/frontline/bookings-virtual-appointments#scheduled-appointment-type) 和排定的個別約會中視需要關閉或開啟簡訊通知。

若要設定此設定，請移至 [Microsoft 365 系統管理中心 \> **設定** \> 組織 **] 設定**，然後選擇 **[Bookings]**。 選取或清除 [ **允許 Microsoft 傳送簡訊通知** ] 核取方塊。

深入瞭解如何 [為貴組織設定簡訊通知](/microsoft-365/bookings/turn-bookings-on-or-off)。

## <a name="optional-staff-approvals-setting"></a>選擇性員工核准設定

您可以要求員工在 Bookings 分享其排程可用性資訊之前加入宣告，然後其他人才能與他們排程約會。

若要啟用此設定，請移至 [Microsoft 365 系統管理中心 \> **設定** \> 組織 **] 設定**，然後選擇 **[Bookings]**。 選取 [ **要求員工核准] 複選** 框。

開啟此設定後，教職員會收到一封電子郵件，要求他們核准預約行事曆的成員資格。  

深入瞭解 [如何設定教職員核准設定](/microsoft-365/bookings/turn-bookings-on-or-off)。

## <a name="changing-your-default-domain-when-setting-up-a-bookings-mailbox"></a>設定 Bookings 信箱時變更預設網域

設定 Bookings 信箱時，系統會使用 Microsoft 365 或 Office 365 組織的預設電子郵件網域。 不過，預設網域可能會在傳送會議邀請給外部收件者時造成問題。 例如，您的邀請可能會被標幟為垃圾郵件，並移至收件者的垃圾郵件資料夾，因此收件者可能永遠不會看到您的邀請。

建議您先變更預設網域，再建立 Bookings 信箱。 請參閱 [網域常見問題](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-microsoft-365)。

如果您在建立 Bookings 信箱之後需要變更預設網域，請使用 PowerShell。

```powerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

若要深入瞭解，請參閱 [設定信箱](/powershell/module/exchange/mailboxes/set-mailbox)。

> [!NOTE]
> 如果您使用的是 Exchange 混合式設定，建議您在變更預設網域時，徹底測試內部部署 Exchange 與 Exchange Online 之間的郵件流程。

## <a name="send-feedback"></a>傳送意見反應

歡迎您提供寶貴的意見：

* 使用者體驗或便於使用
* 功能差距或功能遺失
* Bug 或問題
  
若要傳送意見反應，請選取 Teams 左側導覽列底部的 [說明 **] 選項，** 然後選取 [**回報****所有** 問題的問題]。 在您的意見反應報告開頭表示您要傳送有關「Bookings」的意見反應，讓我們可以輕鬆找出 Bookings 問題。

## <a name="related-articles"></a>相關文章

[在瀏覽器上管理 Teams 虛擬約會的加入體驗](/microsoft-365/frontline/browser-join)


  [適用於終端使用者的 Bookings 文件](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
