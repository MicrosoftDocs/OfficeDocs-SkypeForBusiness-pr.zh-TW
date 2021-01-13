---
title: 修改商務用 Skype Server 中的經驗品質設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 摘要：瞭解如何在商務用 Skype Server 中指定 QoE 資料的保留。
ms.openlocfilehash: 18776e9b8eec9dcff6ced9f654d8153d7fa01777
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827793"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>修改商務用 Skype Server 中的經驗品質設定

**摘要：** 瞭解如何在商務用 Skype Server 中指定 QoE 資料的保留。

根據預設，在60天后會清除 (QoE) 資料的經驗品質。 您可以使用 [ **經驗品質資料** ] 頁面上的設定，將資料保留較長或更短的時間週期。 如果您停用 QoE，啟用 QoE 之前所捕獲的資料也會加以清除。

> [!NOTE]
> 您應設定詳細通話記錄 (CDR) 和 QoE 保留相同天數的資料。 [通話詳細資料包告] 中的每個通話 (Cdr) ，可從監控報告首頁取得，包含 CDR 和 QoE 資訊。 如果 CDR 和 QoE 的清除持續時間不同，有些呼叫可能只會包含 CDR 資料，另有可能只包含 QoE 資料。

下列程式說明如何設定 QoE 資料的清除設定。

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台指定 QoE 資料的保留

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱＜**Delegate Setup Permissions**＞。

2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。

3. 在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。

4. 在 [ **經驗品質資料** ] 頁面上，按一下表格中的適當網站，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細** 資料]。

5. 若要開啟清除，請選取 [ **啟用 QoE 的清除**]。

6. 在 [ **保持 QoE 的最大持續時間 (天數])** 選取應該保留 QoE 資料的最大天數。

7. 按一下 **[認可]**。

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指定 QoE 保留

您可以使用 Windows PowerShell 及 **Set CsQoEConfiguration** Cmdlet 來建立 QoE 保留設定。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 商務用 Skype Server 中的程式相同。

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>指定特定位置的 QoE 保留

- 這個命令可讓 Redmond 網站的 QoE 資料得以清除，並設定網站以維護20天的 QoE 資料。

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>若要指定多個位置的 QoE 保留

- 這個命令會針對組織中使用的所有 QoE 設定設定，設定 QoE 保留。

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

如需詳細資訊，請參閱 [Set CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。

## <a name="see-also"></a>另請參閱

[部署監控](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
