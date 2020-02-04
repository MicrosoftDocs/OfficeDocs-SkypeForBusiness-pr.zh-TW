---
title: 移轉回應群組
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c01ec246ba99d2a2f71a16179d839409e6b57b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>移轉回應群組

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

將使用者移至 Lync Server 2013 池之後，您就可以遷移回應群組。 遷移回應群組包括複製代理群組、佇列、工作流程和音訊檔案，以及將回應群組連絡人物件從舊版部署移至 Lync Server 2013 池。 在您遷移舊版回應群組之後，就會透過 Lync Server 2013 池中的回應群組應用程式來處理回應群組的呼叫。 舊版池已不再處理回應群組的呼叫。

<div>


> [!NOTE]  
> 雖然您可以在將所有使用者移至 Lync Server 2013 池之前先遷移回應群組，但我們建議您先移動所有使用者。 特別是，回應群組代理的使用者在移至 Lync Server 2013 池之前，將不會有新功能的完整功能。



</div>

在您遷移回應群組之前，您必須先部署包含回應群組應用程式的 Lync Server 2013 池。 當您部署企業語音時，系統會預設安裝並啟用回應群組應用程式。 您可以執行**CsService – ApplicationServer** Cmdlet，以確保已安裝回應群組應用程式。

<div>


> [!NOTE]  
> 在您遷移舊版回應群組之前，您可以在 Lync Server 2013 池中建立新的 Lync Server 2013 回應群組。



</div>

若要將回應群組從舊版池遷移至 Lync Server 2013，請執行**CsRgsConfiguration** Cmdlet。 您必須先安裝 Windows 管理工具（WMI）回溯相容性介面封裝，才能執行**移動 CsRgsConfiguration**。 若要安裝此應用程式，請執行 OCSWMIBC。 您可以在安裝媒體的 [設定] 資料夾中找到 OCSWMIBC。

<div>


> [!IMPORTANT]  
> 回應群組遷移 Cmdlet 會移動整個池的回應群組設定。 您無法選取要遷移的特定群組、佇列或工作流程。



</div>

在您遷移回應群組之後，您需要更新正式代理程式用來登入和登出其回應群組的 URL，並使用 Lync Server 的 [控制台] 或 [Lync Server 管理命令介面] Cmdlet 來確認所有的代理群組、佇列和工作流程已移動成功.

<div>


> [!WARNING]  
> 當您遷移回應群組時，系統不會移除 Office 通訊伺服器 2007 R2 回應群組。 請勿移除 Office 通訊伺服器 2007 R2 回應群組。 如果您移除 Office 通訊伺服器 2007 R2 回應群組，Lync Server 2013 中的回應群組就會停止運作。



</div>

<div>


> [!IMPORTANT]  
> 我們建議您不要從先前的部署移除任何資料，除非您解除該池。 此外，我們強烈建議您在遷移後立即匯出回應群組。 如果 Office 通訊伺服器 2007 R2 回應群組已移除，您可以從備份中還原回應群組，以取得 Lync Server 2013 回應群組再次執行。



</div>

當您執行**CsRgsConfiguration** Cmdlet 時，系統會在舊版池中保留代理群組、佇列、工作流程和音訊檔案，以供回滾之用。 不過，如果您需要回滾到舊版池，您必須執行**CsApplicationEndpoint** Cmdlet，以將連絡人物件移回舊版資源區。

<div>


> [!IMPORTANT]  
> 我們建議您不要從舊版池中刪除任何回應群組資料，直到您解除該池為止。



</div>

針對遷移回應群組設定所遵循的程式，假設您的舊版池與 Lync Server 2013 池之間有一對一關聯性。 如果您打算在您的遷移和部署期間合併或分割池，您需要規劃哪些舊版池會對應到哪個 Lync Server 2013 池。

<div>

## <a name="to-migrate-response-group-configurations"></a>若要遷移回應群組設定

1.  在安裝媒體的 Setup 資料夾中找到 OCSWMIBC，然後進行安裝。

2.  以 RTCUniversalServerAdmins 群組成員的帳戶登入電腦，或擁有同等的系統管理員許可權和許可權。

3.  開啟 Lync Server 管理命令介面。

4.  在命令列中，輸入下列內容：
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    例如：
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  如果您在 Office 通訊伺服器 2007 R2 環境中部署 Microsoft Office Communicator 2007 R2 的 [回應群組] 索引標籤，請從 Office Communicator 2007 R2 索引標籤 .xml 檔案中移除索引標籤。
    
    <div>
    

    > [!NOTE]  
    > 正式代理程式使用 [回應群組] 索引標籤登入其回應群組，然後才能接聽來電。 如果您已部署 [回應群組] 索引標籤，就表示您在部署 Office Communicator 2007 R2 索引標籤 .xml 檔案時，選擇該位置。

    
    </div>

6.  為使用者提供由代理程式登入和登出其回應群組所需的更新 URL。
    
    <div>
    

    > [!NOTE]  
    > URL 通常https://webpoolFQDN/RgsClients/Tab.aspx是，其中 webpoolFQDN 是與您剛剛遷移至 Lync Server 2013 之池相關聯之網頁池的完整功能變數名稱（FQDN）。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在使用者升級至 Lync 2013 之後，不需要此步驟，因為 URL 可從 Lync 中的 [<STRONG>工具</STRONG>] 功能表取得。

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 驗證回應群組的遷移

1.  開啟 [Lync Server 控制台]。

2.  在左側功能窗格中，按一下 [**回應群組**]。

3.  在 [**工作流程**] 索引標籤上，確認您的 Office 通訊伺服器 2007 R2 環境中的所有工作流程都包含在清單中。

4.  按一下 [**佇列**] 索引標籤，並確認您的 Office 通訊伺服器 2007 R2 環境中的所有佇列都包含在清單中。

5.  按一下 [**群組**] 索引標籤，並確認您的 Office 通訊伺服器 2007 R2 環境中的所有代理群組都包含在清單中。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>使用 Cmdlet 驗證回應群組遷移

1.  開啟 Lync Server 管理命令介面。
    
    如需有關下列 Cmdlet 的詳細資訊，請執行：
    
        Get-Help <cmdlet name> -Detailed

2.  在命令列中，輸入下列內容：
    
        Get-CsRgsAgentGroup

3.  確認您的 Office 通訊伺服器 2007 R2 環境中的所有代理群組都包含在清單中。

4.  在命令列中，輸入下列內容：
    
        Get-CsRgsQueue

5.  確認您的 Office 通訊伺服器 2007 R2 環境中的所有佇列都包含在清單中。

6.  在命令列中，輸入下列內容：
    
        Get-CsRgsWorkflow

7.  確認您的 Office 通訊伺服器 2007 R2 環境中的所有工作流程都包含在清單中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

