---
title: 在商務用 Skype Server 中啟用呼叫詳細資料錄製
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 摘要：瞭解如何在商務用 Skype Server 中啟用通話詳細資料錄製（CDR）記錄。
ms.openlocfilehash: 015ac3b57420401894e82c267e9737990ca7affb
ms.sourcegitcommit: 332817f49ec1e6767334fdd4c2ec3f791020a26c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/05/2019
ms.locfileid: "36767055"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用呼叫詳細資料錄製

**摘要：** 瞭解如何在商務用 Skype Server 中啟用通話詳細資料錄製（CDR）記錄。

通話詳細資料錄製（CDR）記錄對等活動的用法與診斷資訊，包括實例訊息、透過網際網路通訊協定（VoIP）通話、應用程式共用、檔案傳輸及會議。 使用資料可用來計算投資回報率（ROI），而診斷資料可用來針對對等活動和會議進行疑難排解。

使用下列程式可為您的整個組織或貴組織中的每個網站啟用 CDR。

> [!NOTE]
> 若要啟用 CDR，您必須設定監視及監視資料庫。 如需詳細資訊，請參閱[部署監視](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 啟用 CDR

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.

2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**呼叫詳細資料錄製**]。

4. 在 [**通話詳細資料記錄**] 頁面上，從表格中按一下適當的網站，按一下 [**動作**]，然後按一下 [**啟用 CDR**]。

    > [!NOTE]
    > 預設會啟用 CDR。

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 啟用 CDR

您可以使用 Windows PowerShell 和**CsCdrConfiguration** Cmdlet 來啟用 CDR。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中，程式是一樣的。

### <a name="to-enable-cdr-for-a-single-location"></a>若要針對單一位置啟用 CDR

 若要停用 CDR，請將 EnableCDR 參數設定為 True （$True）。

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>若要針對單一位置停用 CDR

 若要停用 CDR，請將 EnableCDR 參數設定為 False （$False）。 停用 CDR 不會卸載監視。 它會暫停 CDR 資料的收集和儲存。

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>若要使用單一命令在多個位置啟用 CDR

 這個命令會針對貴組織中目前使用的所有 CDR 配置設定啟用 CDR。

  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

如需詳細資訊，請參閱[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 的說明主題。

## <a name="see-also"></a>另請參閱

[規劃監視](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[部署監控](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
