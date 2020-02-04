---
title: Lync Server 2013：部署共用線條外觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e0f6aeb7d235ea7691c6878a4f21e6ec98f531e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>在 Lync Server 2013 中部署共用線條外觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-06-13_

請閱讀本主題，瞭解如何在 Lync Server 2013 中部署共用線條外觀（SLA），累加更新4月2016。 SLA 是一項功能，可在稱為共用號碼的特定號碼上處理多個通話。

如需此功能的詳細資訊，請參閱[Lync Server 2013 中的共用線條外觀規劃](lync-server-2013-plan-for-shared-line-appearance.md)。

共用線路外觀（SLA）是 Lync Server 2013 中的新功能，累積更新4月2016。 若要啟用此功能，您必須先部署此累積更新。

<div>

## <a name="install-shared-line-appearance"></a>安裝共用線條外觀

1.  在 Lync Server 2013 之後，將部署 4 2016 月的累計更新，且預設不會啟用 SLA 應用程式。 若要啟用應用程式，請遵循下列步驟：
    
    1.  針對每個池執行下列命令，以伺服器應用程式的方式來註冊 SLA：
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        其中% FQDN% 是該池的完整功能變數名稱。
    
    2.  執行下列命令以更新 SLA Cmdlet 的 RBAC 角色：
        ```powershell
        Update-CsAdminRole 
        ```
    3.  在已安裝並啟用 SLA 的所有池中，重新開機所有前端伺服器（RTCSRV 服務）：
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>建立 SLA 群組並新增使用者

1.  使用[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) CMDLET 建立 SLA 群組：
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    CsSlaConfiguration Cmdlet 會將企業語音帳戶 SLAGroup1 為 SLA 實體，而 SLAGroup1 的數量會成為 SLA 群組的數位。 SLAGroup1 的所有呼叫都會撥打整個 SLA 群組。
    
    下列範例會建立現有企業語音使用者的 SLA 群組，SLAGroup1，並使用指派給 SLAGroup1 的號碼做為 SLA 主線編號。
    
    此命令會將新 SLA 群組的最大併發呼叫數量設為3，並將超過該限制的通話數設定為聽到占線信號：
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    您可以使用 [設定] CsSlaConfiguration 來建立新的 SLA 群組或修改現有的 SLA 群組。
    
    <div>
    

    > [!NOTE]  
    > 請注意，您指定的<CODE>-Identity</CODE>內容必須是有效的現有企業語音使用者帳戶。

    
    </div>

2.  使用[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) Cmdlet 在群組中新增代理人：
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    下列範例會將使用者新增至 SLA 群組。 新增至群組的每個使用者都必須是有效的企業語音使用者：
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    針對您要新增到群組的每個使用者重複此 Cmdlet。 使用者只能屬於單一的 SLA 群組。

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>設定 SLA 群組 Busy 選項

1.  使用[CsSlaConfiguration Cmdlet 設定](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration)SLA 群組 Busy 選項：
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    下列範例會將超過最大併發呼叫數的來電轉接到電話號碼202-555-1234。 目標可能是貴組織中的使用者，而不是電話號碼;在這種情況下，收件者接收轉寄來電的語法就與您指定代理人的方式相同： `sip:<NameofDelegate@domain>`。 其他可能的參數`BusyOption`為： `Voicemail`
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>設定 SLA 群組 [未接來電] 選項

1.  使用[CsSlaConfiguration Cmdlet 設定](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration)SLA 群組未接來電選項：
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    下列範例指定將未接來電轉寄給名為`sla_forward_number`的使用者。 `-MissedCallOption`參數的有效選項為`Forward`、 `BusySignal`或`Disconnect`。 如果您選擇`Forward`，您也必須包含`-MissedCallForwardTarget`參數，並將使用者或電話號碼做為目標：
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>從群組中移除代理人

1.  使用[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) Cmdlet 移除群組中的代理人：
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    例如：
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a>刪除 SLA 群組

1.  使用[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) CMDLET 刪除 SLA 群組：
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    例如：
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

