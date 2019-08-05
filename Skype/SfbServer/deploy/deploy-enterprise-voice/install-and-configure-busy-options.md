---
title: 安裝及設定商務用 Skype Server 的 Busy 選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: 瞭解如何在商務用 Skype Server 中安裝及設定 Busy 選項。
ms.openlocfilehash: 13f529ddd7bd3b83f9d065599d3a213662da31a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189331"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>安裝及設定商務用 Skype Server 的 Busy 選項

瞭解如何在商務用 Skype Server 中安裝及設定 Busy 選項。

[忙碌選項] 是一種新的語音策略, 在2016年7月累計更新中引進, 可讓您設定當使用者已在通話或會議中, 或有來電處於保留狀態時, 處理來電的方式。 您可以使用占線信號或轉接至語音信箱來拒絕新的或來電的通話。

如果組織已啟用 [忙碌] 選項, 企業中的所有使用者 (企業語音和非企業語音使用者) 都可以使用下列設定選項:

- 繁忙-在此情況下, 如果使用者太忙, 就會拒絕新的傳入通話。

- 占線時的語音信箱-當使用者忙碌時, 會將新的撥入電話轉寄到語音信箱。

不論其忙碌選項的設定方式為何, 通話或會議中的使用者, 或通話保持通話的使用者, 都不會被禁止開始新的通話或會議。

如需繁忙選項功能的詳細資訊, 請參閱[規劃商務用 Skype Server 的繁忙選項](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)。

## <a name="install"></a>安裝

確定您已安裝最新版本的商務用 Skype Server, 且您已安裝最新的修補程式。 若要這樣做, 請先停止所有服務, 然後執行商務用 Skype Server 更新安裝程式, 如下所示:

1. 執行 [停止 CsWindowsService] 命令。

2. 在池中的每個前端伺服器上執行 SkypeServerUpdateInstaller 安裝程式。

3. 如果您想要確保在 SBS 上的容錯移轉支援, 請在每個 Survivable 分支伺服器 (SBS) 上執行 SkypeServerUpdateInstaller 安裝程式。

安裝程式將會部署最新版本的 [Busy 選項] 應用程式。 不過, 預設不會啟用應用程式。 若要啟用應用程式, 請執行下列步驟:

1. 執行[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) Cmdlet 來全域啟用 Busy 選項, 如下列範例所示:

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. 接著, 如果網站有語音原則, 您必須為語音原則啟用 Busy 選項, 如下所示:

    首先, 請執行[CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)以取得網站名稱:

   ```
   Get-CsSite
   ```

    使用身分識別值 (例如: Site: Redmond1) 從 CsSite 中檢索, 以取得網站的語音原則, 如下所示:

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    如果網站有語音原則, 請執行下列命令:

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. 接著, 執行[新的 CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) Cmdlet, 在伺服器應用程式清單中新增 Busy 選項, 如下列範例所示:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > 您必須以特定池的完整功能變數名稱取代% FQDN%。

4. 接著, 執行[CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) Cmdlet 來更新適用于 Busy 選項 Cmdlet 的角色式存取控制 (RBAC) 角色, 如下列範例所示:

   ```
   Update-CsAdminRole
   ```

5. 最後, 執行 [[開始-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) ] 命令, 在已安裝及啟用 [忙碌] 選項的所有池中, 啟動所有前端伺服器上的商務用 Skype Server Windows 服務:

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a>設定

若要設定 Busy 選項, 請使用[CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) Cmdlet。

例如, 下列命令會設定使用者「Ken Myer」的 busy 選項。 在這個設定中, 任何對 "Ken Myer" 的呼叫都會在他已在通話中時傳回占線信號:

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

在下一個範例中, 命令會為使用者 [Chrystal Velasquez] 設定 busy 選項。 在此設定中, 當她已在通話中時, 會將來電轉接至 [Chrystal Velasquez] 的新來電:

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

您可以使用[CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) Cmdlet 來取得有關 Busy 選項的設定資訊。 下列範例會傳回 "KenMyer@Contoso.com" 的 Busy 選項設定:

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

您可以使用[CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) Cmdlet 來移除 Busy 選項。 下列命令會移除「Ken Myer」的 Busy 選項:

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

如需用來設定 Busy 選項之 Cmdlet 的詳細資訊, 請參閱[設定 CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)、 [CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)及[移除 CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)的技術參考內容。

## <a name="enable-logging"></a>啟用記錄功能

若要使用集中式記錄服務啟用 [忙碌] 選項的記錄, 請指定下列專案:

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>驗證及疑難排解

安裝 Busy 選項之後, 您可以使用[CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) Cmdlet 來取得伺服器應用程式的清單, 以驗證安裝成功。 如果 [忙碌] 選項已正確安裝, 則 Cmdlet 的輸出應該會顯示 [忙碌選項] 設定, 如下所示:

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

您也可以使用 Windows 事件檢視器, 確認 [忙碌] 選項安裝已成功, 且商務用 Skype 伺服器已順利載入 Busy 選項。 若要驗證 Busy 選項, 請開啟**事件\>檢視器-應用程式\>和服務記錄-Skype (或 Lync) 伺服器**, 並搜尋事件 ID = 30253。
