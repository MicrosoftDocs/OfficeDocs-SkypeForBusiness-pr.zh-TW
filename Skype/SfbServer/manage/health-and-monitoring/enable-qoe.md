---
title: 在商務用 Skype Server 中啟用體驗品質
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 摘要：瞭解如何在商務用 Skype Server 中啟用體驗品質（QoE）。
ms.openlocfilehash: bc757748e9d95c92405a7dc9a72f87b869165825
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817963"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用體驗品質

**摘要：** 瞭解如何在商務用 Skype Server 中啟用體驗品質（QoE）。

經驗品質（QoE）會記錄數位資料，指出媒體質量與參與者的相關資訊、裝置名稱、驅動程式、IP 位址，以及通話和會話中所涉及的端點類型。 如需詳細資訊，請參閱規劃檔中的[監控規劃](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)。

使用下列程式為您的整個組織或貴組織中的每個網站啟用 QoE。

> [!NOTE]
> 若要啟用 QoE，您必須先設定監視及監視後端資料庫。 如需詳細資訊，請參閱[部署監視](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 啟用 QoE

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.

2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**體驗資料品質**]。

4. 在 [**體驗品質資料**] 頁面上，按一下表格中的適當集合，按一下 [**動作**]，然後按一下 [**啟用 QoE**]。

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 啟用 QoE

您可以使用 Windows PowerShell 和**CsQoEConfiguration** Cmdlet 來啟用 QoE。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中，程式是一樣的。

### <a name="to-enable-qoe-for-a-single-location"></a>若要針對單一位置啟用 QoE

 若要啟用 QoE，請將 EnableQoE 參數設定為 True （$True）。

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>針對單一位置停用 QoE

 若要停用 QoE，請將 EnableQoE 參數設定為 False （$False）。 這不會卸載監視。 它會暫停 QoE 資料的收集和儲存。

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>若要在多個位置使用單一命令來啟用 QoE

 這個命令會針對貴組織中目前使用的所有 QoE 設定設定啟用 QoE。

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

如需詳細資訊，請參閱[設定 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。

## <a name="see-also"></a>另請參閱

[規劃監視](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[部署監控](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

