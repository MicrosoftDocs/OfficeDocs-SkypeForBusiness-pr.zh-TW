---
title: 移轉回應群組
description: 遷移回應群組。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19da4d39b6f11931bffb5a6e422c2826e7351d69
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570319"
---
# <a name="migrate-response-groups"></a>移轉回應群組

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-23_

將使用者移至 Lync Server 2013 集區之後，您可以遷移回應群組。 遷移回應群組包括從舊版部署到 Lync Server 2013 集區，將代理群組、佇列、工作流程、音訊檔及移動回應群組連絡人物件。 遷移舊版回應群組之後，對回應群組的呼叫會由 Lync Server 2013 集區中的回應群組應用程式來處理。 舊版集區不會再處理對回應群組的通話。

<div>


> [!NOTE]  
> 雖然您可以在將所有使用者移至 Lync Server 2013 集區之前遷移回應群組，我們建議您先移動所有使用者。 特別是，回應群組代理的使用者在將新功能移至 Lync Server 2013 集區之前，將不會有其完整功能。



</div>

在遷移回應群組之前，您必須已部署包含回應群組應用程式的 Lync Server 2013 集區。 當您部署企業語音時，預設會安裝及啟用回應群組應用程式。 您可以執行 **Get-CsService – ApplicationServer** Cmdlet 來確定是否已安裝回應群組應用程式。

<div>


> [!NOTE]  
> 您可以在遷移舊版回應群組之前，先在 Lync Server 2013 集區中建立新的 Lync Server 2013 回應群組。



</div>

若要將回應群組從舊版集區遷移至 Lync Server 2013，您需要執行 **Move-CsRgsConfiguration** Cmdlet。

<div>


> [!IMPORTANT]  
> 回應群組遷移 Cmdlet 會移動整個集區的回應群組設定。 您無法選取要移轉的特定群組、佇列或工作流程。



</div>

遷移回應群組之後，您必須使用 Lync Server 控制台或 Lync Server 管理命令介面 Cmdlet，確認所有代理程式群組、佇列和工作流程都已順利移動。

當您遷移回應群組時，不會移除 Lync Server 2010 回應群組。 當您在遷移之後使用 Lync Server 控制台或 Lync Server 管理命令介面來管理回應群組時，您可以看到 Lync Server 2010 回應群組和 Lync server 2013 回應群組。 您應該只將更新套用至 Lync Server 2013 回應群組。 Lync Server 2010 回應群組只會保留以供復原之用。

<div>


> [!WARNING]  
> 完成遷移並建立新的回應群組之後，Lync Server 控制台和 Lync Server 管理命令介面會顯示每個回應群組的 Lync Server 2010 和 Lync Server 2013 版本。 請勿使用 Lync Server 控制台或 Lync Server 管理命令介面來移除 Lync Server 2010 回應群組。 如果您確實移除其中一個，則在遷移期間所建立的對應回應群組將停止運作。 當您解除委任 Lync Server 2010 集區時，將會移除 Lync Server 2010 回應群組。



</div>

<div>


> [!IMPORTANT]  
> 建議集區解除委任之後，再移除先前部署的各項資料。 此外，強烈建議移轉後立即匯出回應群組。 如果 Lync Server 2010 回應群組應該已移除，您可以從備份還原回應群組，讓 Lync Server 2013 回應群組再次執行。



</div>

Lync Server 2013 引進新的回應群組功能，稱為 **工作流程類型**。 **[工作流程類型]** 可以是 **[已管理]** 或 **[未管理]**。 移轉後的所有回應群組 **[工作流程類型] **都會設為 **[未管理]**，並附有一份空白的管理員清單。

執行 **Move-CsRgsConfiguration** Cmdlet 時，代理人群組、佇列、工作流程及音訊檔案都會保留在舊版集區供復原作業使用。 如果確實有必要復原舊版集區，必須執行 **Move-CsApplicationEndpoint** Cmdlet 才能將連絡人物件移動到舊版集區。

下列遷移回應群組設定的程式假設您的舊版集區與 Lync Server 2013 集區之間具有一對一關聯性。 如果您想要在遷移和部署期間整合或分割集區，您需要規劃哪些舊版集區對應到哪些 Lync Server 2013 集區。

<div>

## <a name="to-migrate-response-group-configurations"></a>遷移回應群組設定

1.  使用 RTCUniversalServerAdmins 群組的成員帳戶，或具有等同於系統管理員權限的帳戶登入電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  運行：
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    例如：
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  將回應群組和代理程式遷移至 Lync Server 2013 集區之後，代理人用來登入和登出的 URL 是 Lync Server 2013 URL，可從 [ **工具** ] 功能表取得。 請提醒代理人將書籤等任何參照更新到新的 URL。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>若要使用 Lync Server 控制台驗證回應群組移轉

1.  使用 RTCUniversalReadOnlyAdmins 群組的成員帳戶，或至少必須是 CsViewOnlyAdministrator 角色之成員的帳戶登入電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[回應群組]**。

4.  在 [ **工作流程** ] 索引標籤上，確認您的 Lync Server 2010 環境中的所有工作流程都包含在清單中。

5.  按一下 [ **佇列** ] 索引標籤，並確認您的 Lync Server 2010 環境中的所有佇列都包含在清單中。

6.  按一下 [ **群組** ] 索引標籤，並確認您的 Lync Server 2010 環境中的所有代理程式群組都包含在清單中。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面來驗證回應群組遷移

1.  使用 RTCUniversalReadOnlyAdmins 群組的成員帳戶，或至少必須是 CsViewOnlyAdministrator 角色之成員的帳戶登入電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。
    
    如需下列 Cmdlet 的詳細資料，請執行：
    
        Get-Help <cmdlet name> -Detailed

3.  運行：
    
        Get-CsRgsAgentGroup

4.  確認您的 Lync Server 2010 環境中的所有代理程式群組都包含在清單中。

5.  運行：
    
        Get-CsRgsQueue

6.  確認您的 Lync Server 2010 環境中的所有佇列都包含在清單中。

7.  運行：
    
        Get-CsRgsWorkflow

8.  確認您的 Lync Server 2010 環境中的所有工作流程都包含在清單中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

