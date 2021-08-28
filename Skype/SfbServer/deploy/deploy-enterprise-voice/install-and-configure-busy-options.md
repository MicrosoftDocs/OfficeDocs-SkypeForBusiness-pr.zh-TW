---
title: 安裝及設定商務用 Skype Server 的繁忙選項
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: 請參閱如何在商務用 Skype Server 中安裝及設定忙碌選項。
ms.openlocfilehash: 58c70360a9e25ccefcd62181ab5a1a5b222ae9a5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600678"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>安裝及設定商務用 Skype Server 的繁忙選項

請參閱如何在商務用 Skype Server 中安裝及設定忙碌選項。

「忙碌選項」是在2016累積更新中引進的新語音原則，可讓您設定使用者已在通話或會議中，或有來電暫止的情況下，如何處理來電。 您可以使用繁忙的信號或轉接至語音信箱來拒絕新的或來電的來電。

如果為組織啟用 [忙碌] 選項，則 Enterprise 中的所有使用者（企業語音和非企業語音使用者）均可使用下列設定選項：

- 忙於忙碌-當使用者忙碌時，將會以忙碌信號拒絕新的來電。

- 在忙碌中的語音信箱，當使用者忙碌時，會將新的來電轉送到語音信箱。

不論其忙碌選項的設定方式為何，通話或會議中的使用者或是具有保留狀態的使用者，都不會被禁止撥打新的通話或會議。

如需「忙碌選項」功能的相關資訊，請參閱[Plan for 商務用 Skype Server 的閑選項](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)。

## <a name="install"></a>安裝

請確定已安裝最新版的商務用 Skype Server，且已安裝最新版的修補程式。 若要執行此動作，請先停止所有服務，然後執行商務用 Skype Server 更新安裝程式，如下所示：

1. 執行 Stop-CsWindowsService 命令。

2. 在集區中的每一部前端伺服器上執行 SkypeServerUpdateInstaller.exe 安裝程式。

3. 如果您想要確保 SBS 上的容錯移轉支援，請在每個 Survivable 分支伺服器 (SBS) 上執行 SkypeServerUpdateInstaller.exe 安裝程式。

安裝程式將會部署最新版本的「忙碌選項」應用程式。 不過，預設不會啟用該應用程式。 若要啟用此應用程式，請執行下列步驟：

1. 執行 [Set-CsVoicePolicy](/powershell/module/skype/set-csvoicepolicy?view=skype-ps) Cmdlet 以全域啟用忙碌選項，如下列範例所示：

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. 接下來，如果網站有語音原則，您必須啟用語音原則的「忙碌」選項，如下所示：

    首先，執行 [Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps) 以取得網站的名稱：

   ```powershell
   Get-CsSite
   ```

    使用身分識別值 (例如：從 Get-CsSite 取得的 Site： Redmond1) ，以取得網站的語音原則，如下所示：

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    如果網站有語音原則，請執行下列命令：

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. 接下來，執行 [New-CsServerApplication](/powershell/module/skype/new-csserverapplication?view=skype-ps) Cmdlet 以將忙碌選項新增至伺服器應用程式清單，如下列範例所示：

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > 您必須以特定集區的完整功能變數名稱取代% FQDN%。

4. 接下來，執行 [Update-CsAdminRole](/powershell/module/skype/update-csadminrole?view=skype-ps) Cmdlet 以更新「忙碌」選項 CMDLET (RBAC) 角色的角色型存取控制，如下列範例所示：

   ```powershell
   Update-CsAdminRole
   ```

5. 最後，請執行[Start-CsWindowsService](/powershell/module/skype/start-cswindowsservice?view=skype-ps)命令，在所有已安裝或啟用忙碌選項的集區中，啟動所有前端伺服器上的商務用 Skype Server Windows 服務：

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>設定

若要設定忙碌選項，請使用 [CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) Cmdlet。

例如，下列命令會設定使用者「Ken Myer」的繁忙選項。 在此設定中，任何對「Ken Myer」的呼叫都會在來電已通話時傳回占線信號：

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

在下一個範例中，此命令會為使用者 "Chrystal Velasquez" 設定繁忙選項。 在此設定中，當她已經在通話中時，會將「Chrystal Velasquez」的新來電轉寄到語音信箱：

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

您可以使用 [CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) 指令程式，來取得忙碌選項的設定資訊。 下列範例會傳回 "KenMyer@Contoso.com" 的 [忙碌選項] 設定：

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

您可以使用 [CsBusyOptions 指令程式](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) 移除忙碌選項。 下列命令會移除 "Ken Myer" 的繁忙選項：

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

如需您用來設定忙碌選項之 Cmdlet 的詳細資訊，請參閱 [CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)、 [CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)和 [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)的技術參考內容。

## <a name="enable-logging"></a>啟用記錄

若要使用集中式記錄服務來啟用忙碌選項的記錄，請指定下列各項：

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>驗證及疑難排解

安裝忙碌選項之後，您可以使用 [Get-CsServerApplication](/powershell/module/skype/get-csserverapplication?view=skype-ps) Cmdlet 來取得伺服器應用程式的清單，以確認安裝成功。 如果已正確安裝忙碌選項，指令指令的輸出應會顯示「忙碌選項」設定，如下所示：

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

您也可以使用 Windows 事件檢視器，確認「忙碌選項」安裝順利完成，且商務用 Skype Server 成功載入忙碌選項。 若要驗證忙碌選項，請開啟 [**事件檢視器- \> 應用程式及服務記錄- \> Skype (或 Lync) Server** ，並搜尋 ID= 30253 的事件。