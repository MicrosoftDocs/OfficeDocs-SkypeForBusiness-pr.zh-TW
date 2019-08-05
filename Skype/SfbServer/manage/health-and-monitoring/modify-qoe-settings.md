---
title: 在商務用 Skype Server 中修改體驗品質設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: '摘要: 瞭解如何在商務用 Skype Server 中指定 QoE 資料的保留。'
ms.openlocfilehash: 89e20b18aa285bd4ee61df12c822e487dd6b37a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188782"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中修改體驗品質設定

**摘要:** 瞭解如何在商務用 Skype Server 中指定 QoE 資料的保留。

根據預設, 經驗品質 (QoE) 資料會在60天之後清除。 您可以使用 [**體驗資料品質**] 頁面上的設定, 將資料保留較長或較短的時間週期。 如果您停用 QoE, 則在啟用 QoE 之前捕獲的資料也會受到清除。

> [!NOTE]
> 您應該設定 [通話詳細資料錄製 (CDR)] 和 [QoE], 以保留相同天數的資料。 [監視報告] 首頁提供的呼叫詳細資料包告 (CDRs) 中的每個通話都包含 CDR 和 QoE 資訊。 如果 [CDR] 和 [QoE] 的清除持續時間不一樣, 有些通話可能只會包含 CDR 資料, 而其他可能只包含 QoE 的資料。

下列程式說明如何設定 QoE 資料的清除設定。

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 來指定 QoE 資料的保留

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊, 請參閱**委派設定許可權**。

2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中, 按一下 [**監視及**封存], 然後按一下 [**體驗資料品質**]。

4. 在 [**體驗品質資料**] 頁面上, 從表格中按一下適當的網站, 按一下 [**編輯**], 然後按一下 [**顯示詳細**資料]。

5. 若要開啟清除, 請選取 [**啟用清除 QoE**]。

6. 在 **[保留 QoE 的最大持續時間 (天數)** ] 中, 選取 QoE 資料應保留的最大天數。

7. 按一下 [認可]****。

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指定 QoE 保留

您可以使用 Windows PowerShell 和**CsQoEConfiguration** Cmdlet 來建立 QoE 保留設定。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料, 請參閱博客文章[: 「快速入門: 使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中, 程式是一樣的。

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>若要指定特定位置的 QoE 保留

- 這個命令可讓您清除雷德蒙網站的 QoE 資料, 並將該網站設定為維護20天的 QoE 資料。

  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>若要指定多個位置的 QoE 保留

- 這個命令會針對組織中使用的所有 QoE 設定設定, 設定 QoE 保留。

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

如需詳細資訊, 請參閱[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) Cmdlet 的說明主題。

## <a name="see-also"></a>另請參閱

[部署監控](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
