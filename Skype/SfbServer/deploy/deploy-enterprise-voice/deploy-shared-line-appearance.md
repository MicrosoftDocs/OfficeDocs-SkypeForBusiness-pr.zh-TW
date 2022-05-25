---
title: 在 2015 商務用 Skype Server部署共用線條外觀
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: 閱讀本主題以瞭解如何在 2015 年 11 月累積更新的 商務用 Skype Server 2015 年 11 月部署共用線路外觀 (SLA) 。 SLA 是一項功能，可在稱為共用號碼的特定號碼上處理多個呼叫。
ms.openlocfilehash: 7f9d904de2b3348bdf8ed75b9f0df38aee252cdd
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671589"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>在 2015 商務用 Skype Server部署共用線條外觀

閱讀本主題以瞭解如何在 2015 年 11 月累積更新的 商務用 Skype Server 2015 年 11 月部署共用線路外觀 (SLA) 。 SLA 是一項功能，可在稱為共用號碼的特定號碼上處理多個呼叫。

如需這項功能的詳細資訊，請參閱[規劃 2015 商務用 Skype Server中的共用線條外觀](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)。

共用行外觀 (SLA) 是 2015 年 11 月累積更新商務用 Skype Server的新功能。 若要啟用此功能，您必須先部署此累積更新。

## <a name="install-shared-line-appearance"></a>安裝共用線條外觀

1. 在商務用 Skype Server 2015 年 11 月累積更新之後，請在集區中的每部前端伺服器上執行 `SkypeServerUpdateInstaller.exe` 修補程式。

2. 安裝程式會部署最新版的 SLA 應用程式，但預設不會啟用應用程式。 其啟用方式是遵循下列所述的步驟：

    a. 針對每個集區執行下列命令，將 SLA 註冊為伺服器應用程式：

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   其中 %FQDN% 是集區的完整功能變數名稱。

    b. 執行下列命令來更新 SLA Cmdlet 的 RBAC 角色：

   ```powershell
   Update-CsAdminRole
   ```

    c. 在安裝和啟用 SLA 的所有集區中，重新開機所有前端伺服器 (RTCSRV 服務) ：

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

## <a name="create-an-sla-group-and-add-users-to-it"></a>建立 SLA 群組並將使用者新增至其中

1. 使用 [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) Cmdlet 建立 SLA 群組：

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Set-CsSlaConfiguration Cmdlet 會將企業語音帳戶 SLAGroup1 標示為 SLA 實體，而 SLAGroup1 的數目會變成 SLA 群組的數位。 所有對 SLAGroup1 的呼叫都會響鈴整個 SLA 群組。

    下列範例會為現有的企業語音使用者 SLAGroup1 建立 SLA 群組，並使用指派給 SLAGroup1 的數位作為 SLA 主線號碼。

    命令會將新 SLA 群組的並行呼叫數目上限設定為 3，並將超過該數目的呼叫設定為可聽到忙碌訊號：

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    您可以使用Set-CsSlaConfiguration來建立新的 SLA 群組或修改現有的 SLA 群組。

    > [!NOTE]
    > 請注意，您為 `-Identity` 指定的專案必須是已啟用企業語音的有效現有使用者帳戶。

2. 使用 [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates) Cmdlet 將委派新增至群組：

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
   ```

    下列範例會將使用者新增至 SLA 群組。 新增至群組的每個使用者都必須是啟用企業語音的有效使用者：

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    針對您要新增至群組的每個使用者重複 Cmdlet。 使用者只能屬於單一 SLA 群組。

## <a name="configure-the-sla-group-busy-option"></a>設定 SLA 群組忙碌選項

- 使用 [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) Cmdlet 設定 SLA 群組 Busy 選項：

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    下列範例會設定超過要轉接至電話號碼 202-555-1234 之並行通話數目上限的通話。 目標可能是您組織中的使用者，而不是電話號碼;在此情況下，要接收轉送呼叫的人員語法與指定委派時的語法相同：  `sip:<NameofDelegate@domain>` 。 的另一個可能參數  `BusyOption` 是 `Voicemail` ：

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

## <a name="configure-the-sla-group-missed-call-option"></a>設定 SLA 群組未接來電選項

1. 使用 [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) Cmdlet 設定 SLA 群組未接來電選項：

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 下列範例會指定要將未接來電轉送給名為 的  `sla_forward_number` 使用者。 參數的有效選項為  `-MissedCallOption` `Forward` 、  `BusySignal` 或  `Disconnect` 。 如果您選擇  `Forward` ，則也必須包含  `-MissedCallForwardTarget` 參數，並以使用者或電話號碼作為目標：

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

## <a name="remove-a-delegate-from-a-group"></a>從群組移除委派

- 使用 [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates) Cmdlet 從群組移除委派：

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    例如：

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

## <a name="delete-an-sla-group"></a>刪除 SLA 群組

- 使用 [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration) Cmdlet 刪除 SLA 群組：

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    例如：

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```
