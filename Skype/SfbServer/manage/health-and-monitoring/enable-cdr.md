---
title: 在商務用 Skype Server 中啟用詳細通話記錄
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 摘要：瞭解如何在商務用 Skype Server 中啟用 (CDR) 記錄的詳細通話記錄。
ms.openlocfilehash: 51c2dcd1f1ecf77647ded6dbbc41ea9cdc2c13d8
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014557"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用詳細通話記錄

**摘要：** 瞭解如何在商務用 Skype Server 中啟用 (CDR) 記錄的詳細通話記錄。

詳細通話記錄 (CDR) 會記錄對等活動 (包括立即訊息、VoIP 電話、應用程式共用、檔案傳輸和會議) 的使用方式與診斷資訊。使用方式資料可以用來計算投資報酬率 (ROI)，而診斷資料則可用來排解對等活動和會議的疑難問題。

使用下列程序來為整個組織或組織內的個別網站啟用 CDR。

> [!NOTE]
> 如要啟用 CDR，您必須設定監控及監控資料庫。如需詳細資訊，請參閱＜[Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)＞。

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台啟用 CDR

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3. 在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[詳細通話記錄]**。

4. 在 **[詳細通話記錄]** 頁面上，依序按一下表格中的適當網站、**[動作]** 和 **[啟用 CDR]**。

    > [!NOTE]
    > 預設會啟用 CDR。

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 啟用 CDR

您可以使用 Windows PowerShell 和 **Set-CsCdrConfiguration** Cmdlet 來啟用 CDR。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此指令程式。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱[Microsoft Lync remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 商務用 Skype Server 中的程式相同。

### <a name="to-enable-cdr-for-a-single-location"></a>針對單一位置啟用 CDR

 如要停用 CDR，請將 EnableCDR 參數設為 True ($True)。

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>針對單一位置停用 CDR

 如要停用 CDR，請將 EnableCDR 參數設為 False ($False)。 停用 CDR 不會卸載監控。 它會暫停 CDR 資料的收集和儲存。

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>使用單一命令啟用多個位置的 CDR

 以下命令會啟用組織中所有目前正在使用之 CDR 組態設定的 CDR。

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

如需詳細資訊，請參閱 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。

## <a name="see-also"></a>另請參閱

[規劃監控](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[部署監控](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)