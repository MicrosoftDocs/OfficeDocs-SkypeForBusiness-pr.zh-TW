---
title: 在商務用 Skype Server 2015 中部署共用線外觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: 請閱讀本主題, 瞭解如何在商務用 Skype Server 2015 (2015 年11月累計更新) 中部署共用線條外觀 (SLA)。 SLA 是一項功能, 可在稱為共用號碼的特定號碼上處理多個通話。
ms.openlocfilehash: 0d7bbc62912614cabaea5218225b1fbfb499c691
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233527"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中部署共用線外觀

請閱讀本主題, 瞭解如何在商務用 Skype Server 2015 (2015 年11月累計更新) 中部署共用線條外觀 (SLA)。 SLA 是一項功能, 可在稱為共用號碼的特定號碼上處理多個通話。

如需此功能的詳細資訊, 請參閱[在商務用 Skype Server 2015 中規劃共用線外觀](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)。

共用線外觀 (SLA) 是商務用 Skype Server 中的新功能, 2015 年11月累計更新。 若要啟用此功能, 您必須先部署此累積更新。

### <a name="install-shared-line-appearance"></a>安裝共用線條外觀

1. 在商務用 Skype Server 之後, 已部署2015年11月累計更新`SkypeServerUpdateInstaller.exe` , 請在池中的每個前端伺服器上執行修補程式。

2. 安裝程式將會部署最新版本的 SLA 應用程式, 但是預設不會啟用該應用程式。 您可以依照以下所述的步驟啟用:

    是. 針對每個池執行下列命令, 以伺服器應用程式的方式來註冊 SLA:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   其中% FQDN% 是該池的完整功能變數名稱。

    乙. 執行下列命令以更新 SLA Cmdlet 的 RBAC 角色:

   ```
   Update-CsAdminRole
   ```

    c-clip. 在已安裝並啟用 SLA 的所有池中, 重新開機所有前端伺服器 (RTCSRV 服務):

   ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>建立 SLA 群組並新增使用者

1. 使用[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) CMDLET 建立 SLA 群組:

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    CsSlaConfiguration Cmdlet 會將企業語音帳戶 SLAGroup1 為 SLA 實體, 而 SLAGroup1 的數量會成為 SLA 群組的數位。 SLAGroup1 的所有呼叫都會撥打整個 SLA 群組。

    下列範例會建立現有企業語音使用者的 SLA 群組, SLAGroup1, 並使用指派給 SLAGroup1 的號碼做為 SLA 主線編號。

    此命令會將新 SLA 群組的最大併發呼叫數量設為 3, 並將超過該限制的通話數設定為聽到占線信號:

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    您可以使用 [設定] CsSlaConfiguration 來建立新的 SLA 群組或修改現有的 SLA 群組。

    > [!NOTE]
    > 請注意, 您指定的`-Identity`內容必須是有效的現有企業語音使用者帳戶。

2. 使用[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) Cmdlet 在群組中新增代理人:

   ```
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    下列範例會將使用者新增至 SLA 群組。 新增至群組的每個使用者都必須是有效的企業語音使用者:

   ```
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    針對您要新增到群組的每個使用者重複此 Cmdlet。 使用者只能屬於單一的 SLA 群組。

### <a name="configure-the-sla-group-busy-option"></a>設定 SLA 群組 Busy 選項

- 使用[CsSlaConfiguration Cmdlet 設定](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)SLA 群組 Busy 選項:

  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    下列範例會將超過最大併發呼叫數的來電轉接到電話號碼202-555-1234。 目標可能是貴組織中的使用者, 而不是電話號碼;在這種情況下, 收件者接收轉寄來電的語法就與您指定代理人的方式相同: `sip:<NameofDelegate@domain>`。 其他可能的參數`BusyOption`為: `Voicemail`

  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>設定 SLA 群組 [未接來電] 選項

1. 使用[CsSlaConfiguration Cmdlet 設定](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)SLA 群組未接來電選項:

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 下列範例指定將未接來電轉寄給名為`sla_forward_number`的使用者。 `-MissedCallOption`參數的有效選項為`Forward`、 `BusySignal`或`Disconnect`。 如果您選擇`Forward`, 您也必須包含`-MissedCallForwardTarget`參數, 並將使用者或電話號碼做為目標:

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>從群組中移除代理人

- 使用[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) Cmdlet 移除群組中的代理人:

  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    例如：

  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>刪除 SLA 群組

- 使用[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) CMDLET 刪除 SLA 群組:

  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    例如：

  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


