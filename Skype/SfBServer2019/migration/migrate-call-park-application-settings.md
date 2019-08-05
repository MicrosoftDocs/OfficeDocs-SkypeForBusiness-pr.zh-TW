---
title: 遷移通話駐留應用程式設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '[通話駐留] 應用程式的遷移包括設定商務用 Skype Server 2019 池, 其中包含已在舊版安裝中上傳的任何自訂音樂保留檔案, 還原服務層級設定並 retargeting 所有通話駐留軌道式商務用 Skype Server 2019 池。 如果已在池中設定自訂的 [封存暫停] 檔案, 則需要將這些檔案複製到新的商務用 Skype Server 2019 池。 此外, 建議您將任何通話駐留自訂的音樂保留檔案從另一個目的地備份, 以保留針對通話駐留上傳的任何自訂音樂保留檔案的個別備份複本。 通話駐留應用程式的自訂音樂保留檔案會儲存在該池的檔案存放區中。 若要將文件庫檔案存放區中的音訊檔案複製到商務用 Skype Server 2019 檔案存放區, 請使用 Xcopy 命令及下列參數:'
ms.openlocfilehash: aa4ac3cfbe6802b8853a8ec8886f8fffe1a20a51
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189082"
---
# <a name="migrate-call-park-application-settings"></a>遷移通話駐留應用程式設定

[通話駐留] 應用程式的遷移包括設定商務用 Skype Server 2019 池, 其中包含已在舊版安裝中上傳的任何自訂音樂保留檔案, 還原服務層級設定並重新導向所有通話駐留軌道式[商務用 Skype Server 2019] 池。 如果已在池中設定自訂的 [封存暫停] 檔案, 則需要將這些檔案複製到新的商務用 Skype Server 2019 池。 此外, 建議您將任何通話駐留自訂的 [封存] 檔案移到另一個目的地, 以保留針對通話駐留上傳的任何自訂音樂保留檔案的個別備份複本。 通話駐留應用程式的自訂音樂保留檔案會儲存在該池的檔案存放區中。 若要將文件庫檔案存放區中的音訊檔案複製到商務用 Skype Server 2019 檔案存放區, 請使用**Xcopy**命令及下列參數: 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

當所有自訂的音訊檔案都已複製到商務用 Skype Server 2019 檔案存放區時, 必須設定商務用 Skype Server 2019 池的通話駐留應用程式設定, 以及與舊版池子相關的通話駐留軌道範圍必須重新指派給商務用 Skype Server 2019 池。

[通話駐留] 應用程式設定包括拾取超時閾值、啟用或停用音樂、最大的呼叫挑選嘗試, 以及超時要求。 您必須使用商務用 Skype Server Management Shell 來管理呼叫駐留應用程式設定, 以執行**CsCpsConfiguration** Cmdlet。 您無法使用商務用 Skype Server [控制台] 管理 [通話駐留應用程式設定]。 

## <a name="reconfigure-the-call-park-service-settings"></a>重新設定通話公園服務設定

1. 從商務用 Skype Server 2019 前端伺服器, 開啟商務用 Skype Server 管理命令介面。

2. 在命令列中, 輸入下列內容:

    > [!NOTE]
    > 如果您的商務用 Skype Server 2019 通話駐留應用程式設定與舊版設定相同, 您可以略過此步驟。 如果針對商務用 Skype Server 2019 與舊版環境, 通話駐留應用程式設定會有所不同, 請使用下面的 Cmdlet 做為範本來更新這些變更。 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

若要將所有通話駐留軌道範圍從舊版池中重新指派到商務用 Skype Server 2019, 您可以使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理] 命令介面。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 的 [控制台] 中的 [重新指派所有通話駐留軌道] 範圍

1. 開啟商務用 Skype Server 的 [控制台]。

2. 在左窗格中, 選取 [**語音功能**]。

3. 選取 [**通話駐留**] 索引標籤。 

4. 針對指派給舊版池中的每個通話駐留軌道範圍, 請編輯**目的地伺服器**設定的 FQDN, 然後選取將處理通話駐留要求的商務用 Skype server 2019 池。 

5. 選取 [**確認**], 儲存變更。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 重新分派所有通話駐留軌道的範圍

1. 開啟商務用 Skype Server 管理命令介面。

2. 在命令列中, 輸入下列內容:

   ```
   Get-CsCallParkOrbit
   ```

    這個 Cmdlet 會列出部署中所有的通話駐留軌道的範圍。 所有設定為舊版池的**CallParkServiceId**和**CallParkServerFqdn**參數的通話駐留軌道式, 都必須重新指派。 

    若要將舊版通話駐留軌道範圍重新指派給商務用 Skype Server 2019, 請在命令列中輸入下列內容:

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

將所有呼叫公園軌道範圍重新指派給商務用 Skype Server 2019 池之後, 通話駐留應用程式的遷移程式將會完成, 而商務用 Skype Server 2019 池會處理所有未來的通話駐留要求。


