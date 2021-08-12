---
title: 移轉通話駐留應用程式設定
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 通話駐留應用程式的遷移包含在舊版安裝中上傳的任何自訂音樂暫止檔案中布建商務用 Skype Server 2019 集區、還原服務等級設定，以及 retargeting 所有通話駐留軌道至商務用 Skype Server 2019 集區。 如果已在集區中設定自訂的已等候音樂檔案，則需要將這些檔案複製到新的商務用 Skype Server 2019 集區。 此外，建議您將所有通話駐留自訂的待進行音樂檔案，備份至另一個目的地，以保留針對通話保留所上傳之任何自訂待等候音樂檔案的個別備份副本。 通話駐留應用程式的自訂等候音樂檔案會儲存在集區的檔案存放區中。 若要將音訊檔從集區檔案存放區複製到商務用 Skype Server 2019 檔案存放區，請使用具有下列參數的 Xcopy 命令：
ms.openlocfilehash: f83e1095361ddd272a35bf9100171c0d06caf003dfae84f19c01b2aa53de7977
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312321"
---
# <a name="migrate-call-park-application-settings"></a>移轉通話駐留應用程式設定

「通話駐留」應用程式的遷移包括布建商務用 Skype Server 2019 集區，其中包含已在舊版安裝中上傳的任何自訂等候音樂檔案，還原服務層級設定，並將所有通話駐留軌道重新導向至商務用 Skype Server 2019 集區。 如果已在集區中設定自訂的已等候音樂檔案，則需要將這些檔案複製到新的商務用 Skype Server 2019 集區。 此外，建議您將所有通話駐留自訂的待進行封存檔案備份到另一個目的地，以保留針對通話駐留上傳之任何自訂待等候音樂檔案的個別備份副本。 通話駐留應用程式的自訂等候音樂檔案會儲存在集區的檔案存放區中。 若要將音訊檔從集區檔案存放區複製到商務用 Skype Server 2019 檔案存放區，請使用具有下列參數的 **Xcopy** 命令： 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

當所有自訂音訊檔案都已複製到商務用 Skype Server 2019 檔案存放區時，必須設定商務用 Skype Server 2019 集區的通話駐留應用程式設定，而且與舊版集區相關聯的通話駐留軌道範圍必須重新指派至商務用 Skype Server 2019 集區。

通話駐留應用程式設定包括收取的超時閾值、啟用或停用等候的音樂、呼叫收取的最大嘗試，以及超時要求。 您必須使用商務用 Skype Server 管理命令介面來管理通話駐留應用程式設定，以執行 **Set-CsCpsConfiguration** Cmdlet。 您無法使用商務用 Skype Server 控制台管理通話駐留應用程式設定。 

## <a name="reconfigure-the-call-park-service-settings"></a>重新設定通話駐留應用程式設定

1. 從商務用 Skype Server 2019 前端伺服器，開啟商務用 Skype Server 管理命令介面。

2. 在命令列輸入下列命令：

    > [!NOTE]
    > 如果您的商務用 Skype Server 2019 通話駐留應用程式設定與舊版設定相同，您可以略過此步驟。 如果商務用 Skype Server 2019 和舊版環境的通話駐留應用程式設定不同，請使用下列 Cmdlet 做為範本以更新這些變更。 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

若要將所有通話駐留軌道範圍從舊版集區重新指派至商務用 Skype Server 2019 集區，您可以使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台重新指派所有通話駐留軌道範圍

1. 開啟商務用 Skype Server 控制台]。

2. 在左窗格中，選取 [語音功能]。

3. 選取 [通話駐留] 索引標籤。 

4. 針對指派給舊版集區的每個通話駐留軌道範圍，編輯 [**目的地伺服器的 FQDN** ] 設定，並選取將處理通話駐留要求的商務用 Skype Server 2019 集區。 

5. 選取 [認可] 以儲存變更。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面重新指派所有通話駐留軌道範圍

1. 開啟商務用 Skype Server 管理命令介面。

2. 在命令列輸入下列命令：

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    此 Cmdlet 會列出部署中的所有通話駐留軌道範圍。 所有已設定為舊版集區之 **CallParkServiceId** 和 **CallParkServerFqdn** 參數的通話駐留軌道都必須重新指派。 

    若要將舊版通話駐留軌道範圍重新指派至商務用 Skype Server 2019 集區，請在命令列中輸入下列命令：

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

將所有通話駐留軌道範圍重新指派至商務用 Skype Server 2019 集區之後，通話駐留應用程式的遷移程式便會完成，且商務用 Skype Server 2019 集區將會處理所有未來的通話駐留要求。


