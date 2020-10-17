---
title: 移轉回應群組
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e06b7cec1b02a194b1bb892af0e60771a15ebd5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527450"
---
# <a name="migrate-response-groups"></a>移轉回應群組

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

將使用者移至 Lync Server 2013 集區之後，您可以遷移回應群組。 遷移回應群組包括複製代理程式群組、佇列、工作流程和音訊檔，以及將舊版部署的回應群組連絡人物件移至 Lync Server 2013 集區。 遷移舊版回應群組之後，對回應群組的呼叫會由 Lync Server 2013 集區中的回應群組應用程式來處理。 舊版集區不會再處理對回應群組的通話。

<div>


> [!NOTE]  
> 雖然您可以在將所有使用者移至 Lync Server 2013 集區之前遷移回應群組，我們建議您先移動所有使用者。 特別是，回應群組代理的使用者在將新功能移至 Lync Server 2013 集區之前，將不會有其完整功能。



</div>

在遷移回應群組之前，您必須已部署包含回應群組應用程式的 Lync Server 2013 集區。 當您部署企業語音時，預設會安裝及啟用回應群組應用程式。 您可以執行 **Get-CsService – ApplicationServer** Cmdlet 來確定是否已安裝回應群組應用程式。

<div>


> [!NOTE]  
> 您可以在遷移舊版回應群組之前，先在 Lync Server 2013 集區中建立新的 Lync Server 2013 回應群組。



</div>

若要將回應群組從舊版集區遷移至 Lync Server 2013，您需要執行 **Move-CsRgsConfiguration** Cmdlet。 在執行 **Move-CsRgsConfiguration** 之前，必須先安裝 Windows Management Instrumentation (WMI) 回溯相容性介面套件。 執行 OCSWMIBC.msi 即可安裝此應用程式。 您可在安裝媒體的安裝資料夾中找到 OCSWMIBC.msi。

<div>


> [!IMPORTANT]  
> 回應群組遷移 Cmdlet 會移動整個集區的回應群組設定。 您無法選取要移轉的特定群組、佇列或工作流程。



</div>

遷移回應群組之後，您必須更新正式代理程式用來登入和登出其回應群組的 URL，並使用 Lync Server 控制台或 Lync Server 管理命令介面 Cmdlet，確認所有代理人群組、佇列和工作流程都已順利移動。

<div>


> [!WARNING]  
> 當您遷移回應群組時，不會移除 Office 通訊伺服器 2007 R2 回應群組。 請勿移除 Office 通訊伺服器 2007 R2 回應群組。 如果您移除 Office 通訊伺服器 2007 R2 回應群組，Lync Server 2013 中的回應群組便會停止運作。



</div>

<div>


> [!IMPORTANT]  
> 建議集區解除委任之後，再移除先前部署的各項資料。 此外，強烈建議移轉後立即匯出回應群組。 如果 Office 通訊伺服器 2007 R2 回應群組已移除，您可以從備份還原回應群組，使 Lync Server 2013 回應群組再次執行。



</div>

執行 **Move-CsRgsConfiguration** Cmdlet 時，代理人群組、佇列、工作流程及音訊檔案都會保留在舊版集區供復原作業使用。 不過如果需要回復舊版集區，則需要執行 **Move-CsApplicationEndpoint** Cmdlet，將連絡人物件移回舊版集區。

<div>


> [!IMPORTANT]  
> 建議您在解除委任集區之後，才從舊版集區刪除任何回應群組資料。



</div>

針對遷移回應群組設定所遵循的程式，假設您在舊版集區和 Lync Server 2013 集區之間具有一對一的關聯性。 如果您想要在遷移和部署期間整合或分割集區，您需要規劃哪些舊版集區對應到哪些 Lync Server 2013 集區。

<div>

## <a name="to-migrate-response-group-configurations"></a>遷移回應群組設定

1.  在安裝媒體的安裝資料夾中找到 OCSWMIBC.msi，然後執行安裝。

2.  使用 RTCUniversalServerAdmins 群組的成員帳戶 (或具有對等系統管理員權限的帳戶) 登入電腦。

3.  開啟 Lync Server 管理命令介面。

4.  在命令列輸入下列命令：
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    例如：
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  如果您已在 Office 通訊伺服器 2007 R2 環境中部署 Microsoft Office Communicator 2007 R2 的 [回應群組] 索引標籤，請從 Office Communicator 2007 R2 tabs.xml 檔案中移除索引標籤。
    
    <div>
    

    > [!NOTE]  
    > 正式代理程式會先使用 [回應群組] 索引標籤來登入回應群組，之後才能接收通話。 如果您已部署 [回應群組] 索引標籤，您會在部署 Office Communicator 2007 R2 tabs.xml 檔案時選擇其位置。

    
    </div>

6.  提供使用者更新過的 URL，以讓代理程式用來登入與登出回應群組。
    
    <div>
    

    > [!NOTE]  
    > URL 通常是指 https://webpoolFQDN/RgsClients/Tab.aspx 與您剛才遷移至 Lync Server 2013 之集區相關聯之網頁集區的完整功能變數名稱 (FQDN) 的 webpoolFQDN。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在使用者升級至 Lync 2013 之後，不需要此步驟，因為您可以從 Lync 的 [ <STRONG>工具</STRONG> ] 功能表中取得 URL。

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台驗證回應群組遷移

1.  開啟 Lync Server 控制台。

2.  在左導覽列中，按一下 **[回應群組]**。

3.  在 [ **工作流程** ] 索引標籤上，確認您的 Office 通訊伺服器 2007 R2 環境中的所有工作流程都包含在清單中。

4.  按一下 [ **佇列** ] 索引標籤，確認清單中包含 Office 通訊伺服器 2007 R2 環境中的所有佇列。

5.  按一下 [ **群組** ] 索引標籤，並確認您的 Office 通訊伺服器 2007 R2 環境中的所有代理程式群組都包含在清單中。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>使用 Cmdlet 驗證回應群組移轉

1.  開啟 Lync Server 管理命令介面。
    
    如需有關下列 Cmdlet 的詳細資訊，請執行：
    
        Get-Help <cmdlet name> -Detailed

2.  在命令列輸入下列命令：
    
        Get-CsRgsAgentGroup

3.  確認您的 Office 通訊伺服器 2007 R2 環境中的所有代理程式群組都包含在清單中。

4.  在命令列輸入下列命令：
    
        Get-CsRgsQueue

5.  確認您的 Office 通訊伺服器 2007 R2 環境中的所有佇列都包含在清單中。

6.  在命令列輸入下列命令：
    
        Get-CsRgsWorkflow

7.  確認您的 Office 通訊伺服器 2007 R2 環境中的所有工作流程都包含在清單中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

