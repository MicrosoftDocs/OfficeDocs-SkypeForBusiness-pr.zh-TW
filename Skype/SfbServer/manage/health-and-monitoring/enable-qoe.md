---
title: 在商務用 Skype Server 中啟用經驗品質
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 摘要：瞭解如何在商務用 Skype Server 中啟用 QoE) 的經驗品質 (。
---

# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用經驗品質

**摘要：** 瞭解如何在商務用 Skype Server 中啟用 QoE) 的經驗品質 (。

經驗品質 (QoE) 會記錄數字資料，指出有關通話與工作階段中所包含參與者、裝置名稱、驅動程式、IP 位址和端點類型的媒體品質和資訊。 如需詳細資訊，請參閱規劃檔中的 [規劃監控](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) 。

請使用下列程式，為您的整個組織或組織中的每個網站啟用 QoE。

> [!NOTE]
> 若要啟用 QoE，您必須先設定監控和監控後端資料庫。 如需詳細資訊，請參閱＜[Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)＞。

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台啟用 QoE

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3. 在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。

4. 在 [ **經驗品質資料** ] 頁面上，按一下表格中的適當集合，按一下 [ **動作**]，然後按一下 [ **啟用 QoE**]。

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 啟用 QoE

您可以使用 Windows PowerShell 和 **CsQoEConfiguration** Cmdlet 來啟用 QoE。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此指令程式。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱[Microsoft Lync remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 商務用 Skype Server 中的程式相同。

### <a name="to-enable-qoe-for-a-single-location"></a>針對單一位置啟用 QoE

 若要啟用 QoE，請將 EnableQoE 參數設定為 True ($True) 。

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>停用單一位置的 QoE

 若要停用 QoE，請將 EnableQoE 參數設定為 False ($False) 。 這不會卸載監控。 它會暫停 QoE 資料的收集和儲存。

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>使用單一命令啟用多個位置的 QoE

 此命令會為組織中目前使用的所有 QoE 設定設定啟用 QoE。

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

如需詳細資訊，請參閱 [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。

## <a name="see-also"></a>另請參閱

[規劃監控](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[部署監控](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)