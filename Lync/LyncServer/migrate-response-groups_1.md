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
ms.openlocfilehash: d537182c4d770d6bc7ffc98f71ea891de6552675
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>移轉回應群組

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-19_

您的使用者移至 Lync Server 2013 的集區之後，您可以移轉回應群組。 移轉回應群組包含複製代理人群組、 佇列、 工作流程及音訊檔案，並將回應群組連絡人物件從舊版部署移至 Lync Server 2013 集區。 在移轉舊版回應群組之後，呼叫回應群組是由 Lync Server 2013 集區中的回應群組應用程式處理。 舊版集區不會再處理對回應群組的通話。

<div>


> [!NOTE]  
> 雖然您可以移轉回應群組，您將所有使用者都移至 Lync Server 2013 集區之前，我們建議您第一次都移動所有使用者。 特別是，回應群組代理程式的使用者將不會有新功能的完整功能，直到它們移至 Lync Server 2013 集區。



</div>

移轉回應群組之前，您必須已部署 Lync Server 2013 集區，其中包含的回應群組應用程式。 回應群組應用程式已安裝並啟用根據預設，當您部署企業語音。 您可以確定回應群組應用程式安裝的是執行**Get-CsService – ApplicationServer**指令程式。

<div>


> [!NOTE]  
> 移轉舊版回應群組之前，您可以在 Lync Server 2013 集區中建立新的 Lync Server 2013 回應群組。



</div>

若要從舊版集區的回應群組移轉到 Lync Server 2013 中，您可以執行**Move-csrgsconfiguration** cmdlet。 在執行 **Move-CsRgsConfiguration** 之前，必須先安裝 Windows Management Instrumentation (WMI) 回溯相容性介面套件。 執行 OCSWMIBC.msi 即可安裝此應用程式。 您可在安裝媒體的安裝資料夾中找到 OCSWMIBC.msi。

<div>


> [!IMPORTANT]  
> 回應群組移轉 cmdlet 移動整個集區的回應群組組態。 您無法選取要移轉的特定群組、佇列或工作流程。



</div>

在移轉回應群組之後，您需要更新正式代理程式用來登入與登出回應群組，並使用 Lync Server Control Panel 或 Lync Server 管理命令介面指令程式來驗證所有代理人群組、 佇列及工作流程已都移動的 URL成功。

<div>


> [!WARNING]  
> 當您移轉回應群組時，不會移除 Office Communications Server 2007 R2 的回應群組。 請勿移除 Office Communications Server 2007 R2 的回應群組。 如果您移除 Office Communications Server 2007 R2 回應群組，請在 Lync Server 2013 中的回應群組會停止運作。



</div>

<div>


> [!IMPORTANT]  
> 建議集區解除委任之後，再移除先前部署的各項資料。 此外，強烈建議移轉後立即匯出回應群組。 如果取得移除 Office Communications Server 2007 R2 回應群組，您就可以從若要取得 Lync Server 2013 回應群組，再執行一次備份，然後還原您的回應群組。



</div>

執行 **Move-CsRgsConfiguration** Cmdlet 時，代理人群組、佇列、工作流程及音訊檔案都會保留在舊版集區供復原作業使用。 不過如果需要回復舊版集區，則需要執行 **Move-CsApplicationEndpoint** Cmdlet，將連絡人物件移回舊版集區。

<div>


> [!IMPORTANT]  
> 建議您在解除委任集區之後，才從舊版集區刪除任何回應群組資料。



</div>

移轉回應群組組態會遵循此程序假設您在舊版的集區與 Lync Server 2013 集區之間有一對一的關係。 如果您計劃合併或分割備份集區移轉和部署期間，您需要哪些舊版集區會對應至哪個 Lync Server 2013 集區的計劃。

<div>

## <a name="to-migrate-response-group-configurations"></a>移轉回應群組設定

1.  在安裝媒體的安裝資料夾中找到 OCSWMIBC.msi，然後執行安裝。

2.  使用 RTCUniversalServerAdmins 群組的成員帳戶 (或具有對等系統管理員權限的帳戶) 登入電腦。

3.  開啟 Lync Server 管理命令介面。

4.  在命令列輸入下列命令：
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    例如：
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  如果您部署 Microsoft Office Communicator 2007 r2 的 [回應群組] 索引標籤 Office Communications Server 2007 R2 環境中，移除 Office Communicator 2007 R2 tabs.xml 檔案] 索引標籤。
    
    <div>
    

    > [!NOTE]  
    > 正式代理程式會先使用 [回應群組] 索引標籤來登入回應群組，之後才能接收通話。 如果您部署 [回應群組] 索引標籤，當您部署選擇 Office Communicator 2007 R2 tabs.xml 檔案的位置。

    
    </div>

6.  提供使用者更新過的 URL，以讓代理程式用來登入與登出回應群組。
    
    <div>
    

    > [!NOTE]  
    > 此 URL 通常是https://webpoolFQDN/RgsClients/Tab.aspx，其中 webpoolFQDN 是與剛移轉至 Lync Server 2013 的集區相關聯的 web 集區的完整的網域名稱 (FQDN)。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 因為 URL 是可從 [<STRONG>工具</STRONG>] 功能表，在 Lync 使用者已升級至 Lync 2013 之後，則不需要此步驟。

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>若要使用 Lync Server 控制台驗證回應群組移轉

1.  開啟 Lync Server Control Panel。

2.  在左導覽列中，按一下 **[回應群組]**。

3.  在 [**工作流程**] 索引標籤，確認清單中包含 Office Communications Server 2007 R2 環境中的所有工作流程。

4.  按一下 [**佇列**] 索引標籤，確認清單中包含 Office Communications Server 2007 R2 環境中的所有佇列。

5.  按一下 [**群組**] 索引標籤，確認清單中包含 Office Communications Server 2007 R2 環境中的所有代理程式群組。

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>使用 Cmdlet 驗證回應群組移轉

1.  開啟 Lync Server 管理命令介面。
    
    如需有關下列 Cmdlet 的詳細資訊，請執行：
    
        Get-Help <cmdlet name> -Detailed

2.  在命令列輸入下列命令：
    
        Get-CsRgsAgentGroup

3.  確認清單中包含 Office Communications Server 2007 R2 環境中的所有代理程式群組。

4.  在命令列輸入下列命令：
    
        Get-CsRgsQueue

5.  確認清單中包含 Office Communications Server 2007 R2 環境中的所有佇列。

6.  在命令列輸入下列命令：
    
        Get-CsRgsWorkflow

7.  確認清單中包含 Office Communications Server 2007 R2 環境中的所有工作流程。

</div>

</div>

<span> </span>

</div>

</div>

</div>

