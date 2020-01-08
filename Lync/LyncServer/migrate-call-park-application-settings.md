---
title: 移轉通話駐留應用程式設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f01429a85b679ae5d3710585db84c17e6e64e34b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a>移轉通話駐留應用程式設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

從 Lync Server 2010 將呼叫駐留應用程式遷移至 Lync Server 2013，包括設定 Lync Server 2013 池以及在 Lync Server 2010 中上傳的任何自訂音樂保留檔案，還原服務層級設定和 retargeting所有呼叫公園軌道式移至 Lync Server 2013 池。 如果您已在 Lync Server 2010 pool 中設定自訂的音樂保留檔案，則需要將這些檔案複製到新的 Lync Server 2013 池。 此外，建議您將來自 Lync Server 2010 的任何通話駐留自訂的音樂保留檔案從 Lync Server 備份到另一個目的地，以保留針對通話駐留上傳的任何自訂音樂保留檔案的個別備份複本。 通話駐留應用程式的自訂音樂保留檔案會儲存在該池的檔案存放區中。 若要將 Lync Server 2010 pool 檔案存放區中的音訊檔案複製到 Lync Server 2013 檔案存放區，請使用**Xcopy**命令及下列參數：

   ```
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

當所有自訂的音訊檔案都已複製到 Lync Server 2013 檔案存放區時，必須設定 Lync Server 2013 池的通話駐留應用程式設定，而且與 Lync Server 2010 pool 相關聯的通話駐留軌道的範圍必須重新指派給Lync Server 2013 pool。

[通話駐留] 應用程式設定包括拾取超時閾值、啟用或停用音樂、最大的呼叫挑選嘗試與超時要求。 您必須使用 Lync Server 管理命令介面來執行**CsCpsConfiguration** Cmdlet，以管理通話駐留應用程式設定。 您無法使用 Lync Server [控制台] 管理 [通話駐留應用程式設定]。

**重新設定通話公園服務設定**

1.  從 Lync Server 2013 前端伺服器，開啟 Lync Server 管理命令介面。

2.  在命令列中，輸入下列內容：
    
    <div>
    

    > [!NOTE]  
    > 如果您的 Lync Server 2013 通話駐留應用程式設定與舊版 Lync Server 2010 設定相同，您可以略過執行此步驟。 如果 Lync Server 2013 和 Lync Server 2010 環境的通話駐留應用程式設定不同，請使用以下 Cmdlet 做為範本來更新這些變更。

    
    </div>
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

若要將所有通話駐留軌道範圍從 Lync Server 2010 pool 重新指派給 Lync Server 2013，您可以使用 Lync Server 的 [控制台] 或 [Lync Server 管理命令介面]。

**使用 Lync Server [控制台] 重新分派所有通話駐留軌道的範圍**

1.  開啟 [Lync Server 控制台]。

2.  在左窗格中，選取 [**語音功能**]。

3.  選取 [**通話駐留**] 索引標籤。

4.  針對指派給 Lync Server 2010 pool 的每個通話駐留軌道範圍，請編輯**目的地伺服器**設定的 FQDN，然後選取將處理通話寄存要求的 Lync Server 2013 池。

5.  選取 [**確認**]，儲存變更。

**使用 Lync Server 管理命令介面重新分派所有通話駐留軌道的範圍**

1.  開啟 Lync Server 管理命令介面。

2.  在命令列中，輸入下列內容：
    
        Get-CsCallParkOrbit
    
    這個 Cmdlet 會列出部署中所有的通話駐留軌道的範圍。 所有已設定為 Lync Server 2010 池之**CallParkServiceId**和**CallParkServerFqdn**參數的通話駐留軌道式，都必須重新分派。
    
    若要將 Lync Server 2010 通話駐留軌道範圍重新指派給 Lync Server 2013 池，請在命令列輸入下列內容：
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

將所有通話駐留軌道範圍重新指派給 Lync Server 2013 池之後，通話駐留應用程式的遷移程式將會完成，而 Lync Server 2013 池會處理所有未來的通話駐留要求。

</div>

<span> </span>

</div>

</div>

</div>

