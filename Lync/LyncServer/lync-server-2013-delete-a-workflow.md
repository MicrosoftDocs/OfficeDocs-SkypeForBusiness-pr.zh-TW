---
title: Lync Server 2013：刪除工作流程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aabb1b46d3f67408d586bada6db3d1efaf0538e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>刪除 Lync Server 2013 中的工作流程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

使用下列其中一個程式來刪除工作流程。

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>若要使用 Lync Server [控制台] 刪除工作流程

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**工作流程**]。

4.  在 [**工作流程**] 頁面上，按一下 [**建立或編輯工作流程**]。

5.  在 [**選取服務**搜尋] 欄位中，輸入包含您要刪除之工作流程之**ApplicationServer**服務的部分或所有名稱。

6.  在服務清單中，按一下您想要的服務，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > [回應群組設定工具] 網頁隨即開啟。 您也可以透過連線至<STRONG>&lt;HTTPs://webPoolFqdn&gt;/RgsConfig</STRONG>，直接從網頁瀏覽器開啟回應群組設定工具網頁。

    
    </div>

7.  在 [**管理現有的工作流程**] 底下，找出您要刪除的工作流程，然後在 [**動作**] 底下，按一下 [**刪除**]。

8.  按一下 **[是]**。

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>使用 Windows PowerShell 刪除工作流程

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令列上執行：
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    例如：
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

