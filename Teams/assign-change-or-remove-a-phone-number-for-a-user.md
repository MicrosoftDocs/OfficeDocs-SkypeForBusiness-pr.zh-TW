---
title: 指派、變更或移除使用者的電話號碼
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davelick, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 瞭解如何指派、變更或移除 Teams 使用者的公司電話號碼，讓外部企業和用戶端可以撥入電話。
ms.openlocfilehash: 1a959fd61200e7718cf1e14586d0060fb0e996ec
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606642"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>指派、變更或移除使用者的電話號碼

當您設定通話方案、運算子連線或電信業者連線行動 (公開預覽版) 時，您會將電話號碼指派給使用者。 在 Microsoft Teams 中，當使用者按一下 [ **通話**] 時，會列出您指派的電話號碼。

本文適用于通話方案、電信業者連線電信業者連線行動 (公開預覽版) 。 如需在直接路由案例中指派、變更或移除使用者電話號碼的相關資訊，請參閱 [啟用使用者的直接路由、語音和語音信箱](./direct-routing-enable-users.md)。

在指派通話方案、運算子連線或電信業者連線行動使用者的號碼之前，您必須先為使用者取得號碼。 如需詳細資訊，請參閱[取得通話方案使用者的號碼](getting-phone-numbers-for-your-users.md)、[設定運算子連線使用者的號碼](operator-connect-configure.md#set-up-phone-numbers)或[為電信業者連線行動使用者設定號碼](operator-connect-mobile-configure.md)。

> [!NOTE]
> 查看使用者是否已指派授權的其中一個方法是移至 Microsoft Teams 系統管理中心> **使用者]**。 如果已指派授權，該授權會顯示在頁面上。  您也可以使用Microsoft 365 系統管理中心。

> [!NOTE]
> 本附注適用于具有內部部署的 Active Directory混合式部署的客戶。 如果您想要將通話方案或運算子連接電話號碼指派給使用者或資源帳戶，您必須確保已移除儲存在使用者或資源帳戶物件上 msRTCSIP-Line 屬性中的任何電話號碼 內部部署的 Active Directory，且變更已同步處理至 Microsoft 365。

## <a name="assign-a-phone-number-to-a-user"></a>指派電話號碼給使用者

將電話號碼指派給使用者時，請確定電話號碼和使用者的使用位置都在同一個國家/地區。

若要使用 Teams 系統管理中心指派號碼：

[!INCLUDE [assign-phone-numbers-to-users-steps](./includes/assign-phone-numbers-to-users-steps.md)]


若要使用 PowerShell 指派數位，請使用 [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) Cmdlet，如下所示：

針對通話方案號碼：

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

針對運算子連線號碼：

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

針對電信業者連線行動數位：

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OCMobile
```

例如：

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550103" -PhoneNumberType OCMobile
```







> [!NOTE]
> 由於 Microsoft 365 和 Teams 之間的延遲，使用者最多可能需要 24 小時才能啟用。 如果 24 小時後未正確指派電話號碼，請參閱 [電話號碼服務中心](https://pstnsd.powerappsportals.com/)。

## <a name="change-a-phone-number-for-a-user"></a>變更使用者的電話號碼

若要使用 Teams 系統管理中心變更使用者的電話號碼：

1. 在左側導覽中，按一下 [ **使用者**]，找出並按兩下您要的使用者，再按一下 [ **帳戶**]，然後在 [一 **般資訊**] 底下記下指派給使用者的電話號碼。

2. 在左側導覽畫面中，按一下 **[語音** \> **電話號碼]**。

3. 在 [ **電話號碼]** 頁面上，選取您在步驟 1 中識別的號碼，然後按一下 [ **編輯]**。

4. 在 [ **編輯** ] 窗格中的 [ **指定物件**] 底下，按一下 **[X** ] 以移除使用者。

5. 按一下 [儲存]。

6. 在 [ **電話號碼]** 頁面上，選取清單中未指派的號碼，然後按一下 [ **編輯]**。

7. 在 [ **編輯** ] 窗格中的 [ **指定物件**] 底下，依顯示名稱或使用者名稱搜尋使用者，然後按一下 [ **指派]**。

8. 若要指派或變更相關聯的緊急位置，請在 [ **緊急位置**] 底下搜尋，然後選取該位置。

      > [!NOTE]
      > 如果您要變更運算子連線或電信業者連線行動使用者的號碼，您可能或無法指派或變更相關聯的緊急位置。 這項功能將視您的運算子而定。 如需詳細資訊，請連絡您的運算子。

9. 按一下 [儲存]。

如需 PowerShell 範例，請參閱 [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)。

## <a name="remove-a-phone-number-from-a-user"></a>移除使用者的電話號碼

若要使用 Teams 系統管理中心移除電話號碼：

1. 在左側導覽中，按一下 [ **使用者**]，找出並按兩下您要的使用者，再按一下 [ **帳戶**]，然後在 [一 **般資訊**] 底下記下指派給使用者的電話號碼。

2. 在左側導覽畫面中，按一下 **[語音** \> **電話號碼]**。

3. 在 [ **電話號碼]** 頁面上，選取您在步驟 2 中識別的號碼，然後按一下 [ **編輯]**。

4. 在 [ **編輯** ] 窗格中的 [ **指定物件**] 底下，按一下 **[X** ] 以移除使用者。

5. 按一下 [儲存]。

如需 PowerShell 範例，請參閱 [Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)。

## <a name="related-topics"></a>相關主題

[什麼是位址驗證？](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)

[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
