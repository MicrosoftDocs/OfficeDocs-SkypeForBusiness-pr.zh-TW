---
title: 移轉通話駐留應用程式設定
description: 遷移通話駐留應用程式設定。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da90ca4ee4dd53451c29b8c39861dc76a17ca3c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579409"
---
# <a name="migrate-call-park-application-settings"></a>移轉通話駐留應用程式設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

從 Lync Server 2010 到 Lync Server 2013 的通話駐留應用程式的遷移包括布建 Lync Server 2013 集區，其中包含已在 Lync Server 2010 中上傳的任何自訂音樂保留檔案，還原服務層級設定，並 retargeting 所有通話駐留軌道至 Lync Server 2013 集區。 如果已在 Lync Server 2010 集區中設定自訂的已等候音樂檔案，則需要將這些檔案複製到新的 Lync Server 2013 集區。 此外，建議您將所有通話駐留自訂的封存檔案從 Lync Server 2010 備份到另一個目的地，以保留針對通話保留所上傳之任何自訂待等候音樂檔案的個別備份副本。 通話駐留應用程式的自訂等候音樂檔案會儲存在集區的檔案存放區中。 若要將 Lync Server 2010 集區檔案存放區的音訊檔複製到 Lync Server 2013 檔存放區，請使用具有下列參數的 **Xcopy** 命令：

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

當所有自訂音訊檔案都複製到 Lync Server 2013 檔案存放區時，必須設定 Lync Server 2013 集區的通話駐留應用程式設定，而且與 Lync Server 2010 集區相關聯的通話駐留軌道範圍必須重新指派至 Lync Server 2013 集區。

通話駐留應用程式設定包括收取的超時閾值、啟用或停用等候的音樂、呼叫收取的最大嘗試及超時要求。 您必須使用 Lync Server 管理命令介面來管理通話駐留應用程式設定，以執行 **Set-CsCpsConfiguration** Cmdlet。 您無法使用 Lync Server 控制台管理通話駐留應用程式設定。

**重新設定通話駐留應用程式設定**

1.  在 Lync Server 2013 前端伺服器上，開啟 Lync Server 管理命令介面。

2.  在命令列輸入下列命令：
    
    <div>
    

    > [!NOTE]  
    > 如果您的 Lync Server 2013 通話駐留應用程式設定與舊版 Lync Server 2010 設定相同，您可以略過執行此步驟。 如果 Lync Server 2013 和 Lync Server 2010 環境的通話駐留應用程式設定不同，請使用下列 Cmdlet 做為範本以更新這些變更。

    
    </div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-EnableMusicOnHold" <LS2010 CPS value> "-MaxCallPickupAttempts" " <LS2010 CPS pickup attempts> -OnTimeoutURI" <LS2010 CPS timeout URI> " ```

若要將所有通話駐留軌道範圍從 Lync Server 2010 集區重新指派至 Lync Server 2013 集區，您可以使用 Lync Server 控制台或 Lync Server 管理命令介面。

**使用 Lync Server 控制台重新指派所有通話駐留軌道範圍**

1.  開啟 [Lync Server 控制台]。

2.  在左窗格中，選取 [語音功能]****。

3.  選取 [通話駐留]**** 索引標籤。

4.  針對指派給 Lync Server 2010 集區的每個通話駐留軌道範圍，編輯 [ **目的地伺服器的 FQDN** ] 設定，並選取要處理通話駐留要求的 Lync Server 2013 集區。

5.  選取 [認可]**** 以儲存變更。

**使用 Lync Server 管理命令介面重新指派所有通話駐留軌道範圍**

1.  開啟 Lync Server 管理命令介面。

2.  在命令列輸入下列命令：
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    此 Cmdlet 會列出部署中的所有通話駐留軌道範圍。 所有已設定為 Lync Server 2010 集區之 **CallParkServiceId** 和 **CallParkServerFqdn** 參數的通話駐留軌道都必須重新指派。
    
    若要將 Lync Server 2010 通話駐留軌道範圍重新指派至 Lync Server 2013 集區，請在命令列中輸入下列命令：
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

將所有通話駐留軌道範圍重新指派至 Lync Server 2013 集區之後，通話駐留應用程式的遷移程式就會完成，Lync Server 2013 集區將會處理所有未來的通話駐留要求。

</div>

<span> </span>

</div>

</div>

</div>

