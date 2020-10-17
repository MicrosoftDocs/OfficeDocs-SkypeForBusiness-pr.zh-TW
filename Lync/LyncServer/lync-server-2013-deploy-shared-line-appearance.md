---
title: Lync Server 2013：部署共用線路外觀
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
ms.openlocfilehash: 15d0bffd92c4c2e2448938c467eec73c9bab1a94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531410"
---
# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>在 Lync Server 2013 中部署共用線路外觀

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-06-13_

閱讀此主題以瞭解如何在 Lync Server 2013 中 (SLA) 部署共用行外觀，累積更新4月2016。 SLA 是一種功能，可用於處理特定號碼（稱為共用號碼）上的多個通話。

如需此功能的相關資訊，請參閱 [在 Lync Server 2013 中規劃共用行外觀](lync-server-2013-plan-for-shared-line-appearance.md)。

共用線路外觀 (SLA) 是 Lync Server 2013 中的新功能，累積更新4月2016。 若要啟用此功能，您必須先部署此累計更新。

<div>

## <a name="install-shared-line-appearance"></a>安裝共用線路外觀

1.  在 Lync Server 2013 中，部署了累計更新4月2016，預設不會啟用 SLA 應用程式。 若要啟用此應用程式，請遵循下列步驟：
    
    1.  針對每個集區執行下列命令，將 SLA 註冊成伺服器應用程式：
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        其中，% FQDN% 是集區的完整功能變數名稱。
    
    2.  執行下列命令，更新 SLA Cmdlet 的 RBAC 角色：
        ```powershell
        Update-CsAdminRole 
        ```
    3.  在所有已安裝並啟用 SLA 的集區中，重新開機所有前端伺服器 (RTCSRV 服務) ：
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>建立 SLA 群組並新增使用者

1.  使用 [CsSlaConfiguration 指令程式](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) 建立 SLA 群組：
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    Set-CsSlaConfiguration Cmdlet 會將 Enterprise Voice 帳戶 SLAGroup1 標示為 SLA 實體，SLAGroup1 數目會變成 SLA 群組的數目。 所有對 SLAGroup1 的呼叫都會撥打整個 SLA 群組。
    
    下列範例會為現有的 Enterprise Voice user 和 SLAGroup1 建立 SLA 群組，並使用指派給 SLAGroup1 的號碼做為 SLA 主線編號。
    
    此命令會將新 SLA 群組的並行通話數目上限設定為3，並讓來電超過該限制，以聽到忙碌的信號：
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    您可以使用 Set-CsSlaConfiguration 建立新的 SLA 群組或修改現有的 SLA 群組。
    
    <div>
    

    > [!NOTE]  
    > 請注意，您指定的 <CODE>-Identity</CODE> 必須是有效的現有企業語音使用者帳戶。

    
    </div>

2.  使用 [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) Cmdlet 將委派新增至群組：
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    下列範例會將使用者新增至 SLA 群組。 新增至群組的每個使用者都必須是有效的企業語音啟用使用者：
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    針對您要新增至群組的每個使用者重複此 Cmdlet。 使用者只能屬於單一的 SLA 群組。

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>設定 SLA 群組忙碌選項

1.  使用 [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) Cmdlet 來設定 SLA 群組忙碌選項：
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    下列範例會將超過最大同時呼叫數目轉接的來電設定為電話號碼202-555-1234。 目標可以是您組織中的使用者，而不是電話號碼;在此情況下，接收轉寄呼叫的使用者語法與您指定代理人時的語法相同： `sip:<NameofDelegate@domain>` 。 的其他可能的參數 `BusyOption` 為 `Voicemail` ：
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>設定 SLA 群組未接來電選項

1.  使用 [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) Cmdlet 來設定 SLA 群組未接來電選項：
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    下列範例會指定將未接來電轉寄給名為的使用者 `sla_forward_number` 。 參數的有效選項 `-MissedCallOption` 是 `Forward` 、 `BusySignal` 或 `Disconnect` 。 如果您選擇 `Forward` ，您也必須包含 `-MissedCallForwardTarget` 參數，並以使用者或電話號碼做為目標：
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>從群組中移除代理人

1.  使用 [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) Cmdlet 從群組中移除委派：
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

1.  使用 [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) CMDLET 刪除 SLA 群組：
    
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

