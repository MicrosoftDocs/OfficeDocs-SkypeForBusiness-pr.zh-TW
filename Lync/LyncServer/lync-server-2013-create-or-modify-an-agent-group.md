---
title: Lync Server 2013：建立或修改代理程式群組
description: Lync Server 2013：建立或修改代理程式群組。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a8d3f33df64ba1eacd4fa65a0706d030dc9b5f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574459"
---
# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改代理程式群組

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

使用下列其中一個程式來建立或修改代理程式群組。

<div>


> [!NOTE]  
> 例如，管理員（CsVoiceAdministrator）必須先啟用使用者的 Enterprise Voice 和 Lync Server，使用者才能將使用者指派給代理人群組。 如果您是受管理工作流程的其中一位委派回應群組管理員，您可以在您管理的工作流程中建立代理人群組和使用代理人群組。



</div>

<div>


> [!IMPORTANT]  
> 當您將使用者指派為回應群組代理人時，如果他們已啟用隱私權模式，請通知他們需要搜尋 "RGS Presence Watcher" 連絡人並將他們新增到其連絡人清單。已啟用隱私權模式但其連絡人清單中沒有 "RGS Presence Watcher" 的代理人，無法接收到打給回應群組的電話。未啟用隱私權模式的代理人則不受影響。



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>使用 Lync Server 控制台建立或修改代理程式群組

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。
    
    <div>
    

    > [!NOTE]  
    > 如果您是受管理工作流程的其中一位委派回應群組管理員，您可以在您管理的工作流程中建立群組並加以使用。

    
    </div>

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 **[回應群組]**，然後按一下 **[群組]**。

4.  在 [ **群組** ] 頁面上，執行下列其中一項操作：
    
      - 若要建立新的代理人群組，請按一下 [ **新增**]。 在 [ **選取服務** ] 搜尋欄位中，輸入您要在其中新增群組之 **ApplicationServer** 服務的全部或部分名稱。 在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。
    
      - 若要修改現有的代理人群組，請在 [搜尋] 欄位中輸入 agent 群組的全部或部分名稱。 在產生的清單中，按一下您想要的群組，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。

5.  在 [ **名稱**] 中，輸入代理人群組的識別名稱。

6.  在 **[描述]** 中，輸入群組的描述。

7.  在 **[參與原則]** 中，選取下列其中一項作業來設定群組的登入行為：
    
      - 選取 **[非正式]** 指定群組中的專員不需要登入及登出群組。 當代理人登入 Lync Server 2013 時，會自動登入群組。
    
      - 選取 **[正式]** 指定群組中的專員必須登入和登出群組。 當您選取此選項時，代理程式會按一下 Lync 中的功能表項目以開啟 Internet Explorer，並顯示網頁主控台以供登入和登出群組。

8.  在 **[警示時間 (秒)]** 中，指定專員的電話響幾秒 (預設值為 20 秒) 後會轉給下一個線上專員。
    
    <div>
    

    > [!IMPORTANT]  
    > 「代理程式警示時間」設定不得超過180秒。 如果代理程式警示時間超過180秒，用戶端應用程式會拒絕呼叫，因為 SIP 交易計時器已達到其最長等待時間。

    
    </div>

9.  在 **[路由方法]** 中，選取將電話路由轉送給群組專員的方式，如下所示：
    
      - 若要先對閒置最長 (的代理商提供新呼叫，使其在 Lync Server 中的狀態為 [ **可用** ] 或 [ **非** 使用中] 的時間最長的) ，請按一下 [ **最長閒置**]。
    
      - 若要將新電話同時提供給所有的線上專員，請按一下 **[平行]**。該電話會路由傳送給第一個接聽的專員。
    
      - 若要將新電話輪流提供給每個專員，請按一下 **[循環配置資源]**。
    
      - 若要永遠依照 **[專員]** 清單中的順序將新的來電提供給專員，請按一下 **[序列]**。
    
      - 若要同時登入 Lync Server 2013 和回應群組應用程式的新呼叫，不論其目前目前狀態為何， **請按一下 [** 語音應答]。 設定為代理人的 Lync 2010 語音應答使用者可以查看所有等待的來電，並以任何順序接聽等候通話。 呼叫會傳送給第一個接受它的代理商，之後其他的 Lync 2010 語音應答使用者就不會再看到通話。

10. 在 [ **代理人**] 中，指定您要如何建立代理人清單：
    
      - 若要使用自訂的代理人清單，請按一下 [ **定義代理人的自訂群組**]，然後執行下列其中一項操作：
        
          - 若要將使用者新增至代理人群組，請按一下 [ **選取**]，然後在 [ **選取代理** 搜尋] 欄位中，輸入您要新增至此群組的使用者名稱全部或部分名稱，然後按一下 [ **尋找**]。 在產生的代理程式清單中，按一下使用者，然後按一下 **[確定]**。
        
          - 若要從代理人群組中移除使用者，請在代理程式清單中，按一下您要移除的使用者，然後按一下 [ **移除**]。
        
          - 若要變更代理程式在使用迴圈傳送或串列路由的群組中提供通話的順序，請在代理程式清單中，按一下使用者，然後按一下向上鍵或向下箭號。
    
      - 若要使用 Microsoft Exchange Server 通訊群組清單作為代理人群組，請按一下 [ **使用現有的電子郵件通訊群組清單**]，然後在 [ **通訊群組清單位址**] 中，輸入通訊群組清單的電子郵件地址 (例如，NetworkSupport@contoso.com) 。
        
        如果您使用電子郵件通訊群組清單，您會受到下列限制：
        
          - 您無法為專員群組選取多個通訊群組清單。每一個群組只支援一個通訊群組清單。
        
          - 如果通訊群組清單包含一或多個通訊群組清單，則巢狀通訊群組清單的成員不會加入到專員清單中。
        
          - 如果選取了串列或迴圈複用路由，則伺服器會根據路由方法以及代理列在通訊群組清單中的順序，向適當的代理人提供來電。
        
          - 如果通訊群組清單包含的使用者已啟用 Lync Server 2010，但是未啟用 Enterprise Voice，他們會以 dysfunctional 代理程式的形式新增至代理人群組。 請確定通訊群組清單的所有成員都已啟用企業語音的使用者帳戶。
        
        <div>
        

        > [!IMPORTANT]  
        > 如果您使用電子郵件通訊群組清單，回應群組管理員或使用者可能會看到隱藏的成員資格或隱藏的清單。

        
        </div>
        
        在下列情況下，隱藏的成員資格或隱藏的清單會顯現出來：
        
          - 如果已設定通訊群組清單以便隱藏成員資格，且回應群組管理員將通訊群組清單指派給代理人清單，則使用者可以呼叫群組以找出成員是誰。
        
          - 如果已設定通訊群組清單，使其在 Exchange 全域通訊清單中隱藏，回應群組管理員可能會看到通訊群組清單，並將其指派給代理人清單，如果回應群組處理具有適當的使用者權限，即使系統管理員沒有適當的使用者權限。

11. 按一下 **[認可]**。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>使用 Windows PowerShell 建立或修改代理程式群組

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  使用 **New-CsRgsAgentGroup** 建立新的代理人群組。 使用 **get-csrgsagentgroup** 來修改現有的代理人群組。 在命令列中執行：
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    例如：
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > 「代理程式警示時間」設定不得超過180秒。 如果代理程式警示時間大於180秒，用戶端應用程式會拒絕呼叫，因為 SIP 交易計時器已達到其最長等待時間。

    
    </div>

4.  確認已建立代理人群組。 運行：
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中刪除代理群組](lync-server-2013-delete-an-agent-group.md)  


[在 Lync Server 2013 中管理回應群組代理群組](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[Get-csrgsagentgroup](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

