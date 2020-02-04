---
title: 移轉回應群組
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ef26b86b1de3fa7f9656cdb2ea82bb7a220948
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>移轉回應群組

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-23_

將使用者移至 Lync Server 2013 池之後，您就可以遷移回應群組。 遷移回應群組包括複製代理群組、佇列、工作流程、音訊檔案，以及將回應群組連絡人物件從舊版部署移至 Lync Server 2013 池。 在您遷移舊版回應群組之後，就會透過 Lync Server 2013 池中的回應群組應用程式來處理回應群組的呼叫。 舊版池已不再處理回應群組的呼叫。

<div>


> [!NOTE]  
> 雖然您可以在將所有使用者移至 Lync Server 2013 池之前先遷移回應群組，但我們建議您先移動所有使用者。 特別是，回應群組代理的使用者在移至 Lync Server 2013 池之前，將不會有新功能的完整功能。



</div>

在您遷移回應群組之前，您必須先部署包含回應群組應用程式的 Lync Server 2013 池。 當您部署企業語音時，系統會預設安裝並啟用回應群組應用程式。 您可以執行**CsService – ApplicationServer** Cmdlet，以確保已安裝回應群組應用程式。

<div>


> [!NOTE]  
> 在您遷移舊版回應群組之前，您可以在 Lync Server 2013 池中建立新的 Lync Server 2013 回應群組。



</div>

若要將回應群組從舊版池遷移至 Lync Server 2013，請執行**CsRgsConfiguration** Cmdlet。

<div>


> [!IMPORTANT]  
> 回應群組遷移 Cmdlet 會移動整個池的回應群組設定。 您無法選取要遷移的特定群組、佇列或工作流程。



</div>

在您遷移回應群組之後，您必須使用 Lync Server 的 [控制台] 或 [Lync Server 管理命令介面] Cmdlet，確認所有的代理程式群組、佇列和工作流程已順利移動。

當您遷移回應群組時，不會移除 Lync Server 2010 回應群組。 當您使用 Lync Server [控制台] 或 [Lync Server 管理命令介面] 遷移之後管理回應群組之後，您可以看到 Lync Server 2010 回應群組和 Lync Server 2013 回應群組。 您應該只將更新套用至 Lync Server 2013 回應群組。 Lync Server 2010 回應群組只會保留以供回滾之用。

<div>


> [!WARNING]  
> 完成遷移並建立新的回應群組之後，Lync server 的 [控制台] 和 [Lync Server 管理命令介面] 會顯示每個回應群組的 Lync Server 2010 和 Lync Server 2013 版本。 請勿使用 Lync Server [控制台] 或 [Lync Server 管理命令介面] 來移除 Lync Server 2010 回應群組。 如果您移除其中一個專案，則在遷移期間建立的對應回應群組就會停止運作。 當您解除 Lync Server 2010 池的授權時，將會移除 Lync Server 2010 回應群組。



</div>

<div>


> [!IMPORTANT]  
> 我們建議您不要從先前的部署移除任何資料，除非您解除該池。 此外，我們強烈建議您在遷移後立即匯出回應群組。 如果 Lync Server 2010 回應群組應該被移除，您可以從備份還原回應群組，讓 Lync Server 2013 回應群組再次執行。



</div>

Lync Server 2013 引入了稱為「**工作流程類型**」的新回應群組功能。 **工作流程類型**可以是**託管**或**非託管**。 [所有回應群組] 都將 [**工作流程類型**] 設定為 [**非託管**]，並使用空的管理員清單進行遷移

當您執行**CsRgsConfiguration** Cmdlet 時，系統會在舊版池中保留代理群組、佇列、工作流程和音訊檔案，以供回滾之用。 不過，如果您需要回滾到舊版池，您必須執行**CsApplicationEndpoint** Cmdlet，以將連絡人物件移回舊版資源區。

下列程式適用于遷移回應群組設定的程式，假設您的舊版池與 Lync Server 2013 池之間有一對一關聯性。 如果您打算在您的遷移和部署期間合併或分割池，您需要規劃哪些舊版池會對應到哪個 Lync Server 2013 池。

<div>

## <a name="to-migrate-response-group-configurations"></a>若要遷移回應群組設定

1.  以 RTCUniversalServerAdmins 群組成員的帳戶登入電腦，或擁有同等的系統管理員許可權和許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    例如：
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  在您將回應群組和代理程式遷移至 Lync Server 2013 文件庫之後，代理程式用來登入和登出的 URL 就是 Lync Server 2013 URL，且可從 [**工具**] 功能表取得。 提醒代理程式將任何參照（例如書簽）更新為新的 URL。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 驗證回應群組的遷移

1.  使用屬於 RTCUniversalReadOnlyAdmins 群組成員的帳戶登入電腦，或最少是 CsViewOnlyAdministrator 角色的成員。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側功能窗格中，按一下 [**回應群組**]。

4.  在 [**工作流程**] 索引標籤上，確認您的 Lync Server 2010 環境中的所有工作流程都包含在清單中。

5.  按一下 [**佇列**] 索引標籤，並確認您的 Lync Server 2010 環境中的所有佇列都包含在清單中。

6.  按一下 [**群組**] 索引標籤，並確認您的 Lync Server 2010 環境中的所有代理群組都包含在清單中。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面驗證回應群組遷移

1.  使用屬於 RTCUniversalReadOnlyAdmins 群組成員的帳戶登入電腦，或最少是 CsViewOnlyAdministrator 角色的成員。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。
    
    如需有關下列 Cmdlet 的詳細資訊，請執行：
    
        Get-Help <cmdlet name> -Detailed

3.  用盡
    
        Get-CsRgsAgentGroup

4.  確認您的 Lync Server 2010 環境中的所有代理群組都包含在清單中。

5.  用盡
    
        Get-CsRgsQueue

6.  確認您的 Lync Server 2010 環境中的所有佇列都包含在清單中。

7.  用盡
    
        Get-CsRgsWorkflow

8.  確認您的 Lync Server 2010 環境中的所有工作流程都包含在清單中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

