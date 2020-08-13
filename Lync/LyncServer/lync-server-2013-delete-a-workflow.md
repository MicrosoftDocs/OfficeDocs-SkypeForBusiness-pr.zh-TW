---
title: Lync Server 2013：刪除工作流程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1f3265591b1beb7180864b8e3a613989dfca397
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>在 Lync Server 2013 中刪除工作流程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

請使用下列其中一個程序來刪除工作流程：

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>使用 Lync Server 控制台刪除工作流程

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 **[回應群組]**，然後按一下 **[工作流程]**。

4.  在 **[工作流程]** 頁面上，按一下 **[建立或編輯工作流程]**。

5.  在 **[選取服務]** 搜尋欄位中，輸入裝載您要刪除之工作流程的 **ApplicationServer** 服務的部分或完整名稱。

6.  在服務清單中，按一下所需的服務，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > [回應群組設定工具] 網頁隨即開啟。 您也可以連線到<STRONG>Https:// &lt; webPoolFqdn &gt; /RgsConfig</STRONG>，直接從網頁瀏覽器開啟回應群組設定工具網頁。

    
    </div>

7.  在 **[管理現有的工作流程]** 下，找出您要刪除的工作流程，然後按一下 **[執行]** 下的 **[刪除]**。

8.  按一下 **[是]**。

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>使用 Windows PowerShell 刪除工作流程

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令列中執行：
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    例如：
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

