---
title: Lync Server 2013：建立或修改代理群組
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
ms.openlocfilehash: 99fed5bf80979ef807f45ce7e5ecdc8e8a16329b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改代理群組

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

使用下列其中一個程式來建立或修改代理群組。

<div>


> [!NOTE]  
> 系統管理員（例如 CsVoiceAdministrator）必須先啟用企業語音和 Lync 伺服器的使用者，才能將使用者指派給代理群組。 如果您是受管理工作流程的委派回應群組管理員之一，您可以建立代理群組，並在您管理的工作流程中使用代理群組。



</div>

<div>


> [!IMPORTANT]  
> 當您將使用者指派為回應群組代理程式時，如果他們已啟用隱私權模式，就必須搜尋「RGS 目前狀態觀察程式」連絡人，然後將他們新增到他們的連絡人清單。 已啟用隱私權模式的代理，但其 [連絡人] 清單中沒有「RGS 目前狀態觀察程式」，就無法接收回應群組的呼叫。 未啟用隱私權模式的代理不會受到影響。



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>使用 Lync Server [控制台] 來建立或修改代理群組

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。
    
    <div>
    

    > [!NOTE]  
    > 如果您是受管理工作流程的委派回應群組管理員之一，您可以在您管理的工作流程中建立群組並使用。

    
    </div>

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**群組**]。

4.  在 [**群組**] 頁面上，執行下列其中一項操作：
    
      - 若要建立新的 [代理] 群組，請按一下 [**新增**]。 在 [**選取服務**搜尋] 欄位中，輸入您要新增群組之**ApplicationServer**服務的全部或部分名稱。 在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。
    
      - 若要修改現有的 [代理] 群組，請在 [搜尋] 欄位中輸入 [代理] 群組的全部或部分名稱。 在產生的清單中，按一下您想要的群組，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**名稱**] 中，輸入 [代理] 群組的識別名稱。

6.  在 [**描述**] 中，輸入群組的描述。

7.  在**參與原則**中，選取下列其中一個選項，為群組設定登入行為：
    
      - 選取 [**非正式**]，指定群組中的代理不需要登入和登出群組。 當代理登入 Lync Server 2013 時，系統會自動登入該群組。
    
      - 選取 [**正式**]，指定群組中的代理程式必須登入和登出群組。 當您選取此選項時，代理程式會按一下 Lync 中的功能表項目來開啟 Internet Explorer，並顯示可登入和登出群組的網頁主控台。

8.  在 [**警示時間（秒）**] 中，指定在向下一個可用的代理程式撥打電話之前撥打代理程式的秒數（預設值為20秒）。
    
    <div>
    

    > [!IMPORTANT]  
    > Agent 警示時間設定不能超過180秒。 如果 agent 警示時間超過180秒，用戶端應用程式會拒絕呼叫，因為 SIP 事務計時器達到最大等待時間。

    
    </div>

9.  在**路由方法**中，選取將呼叫路由到群組中的方法，如下所示：
    
      - 若要先為閒置時間最長（在 Lync 伺服器中的目前狀態為「**可用**」或「**非**使用中」）的代理提供新來電，請按一下 [**最長閒置**]。
    
      - 若要同時提供新呼叫給所有可用的代理程式，請按一下 [**平行**]。 電話會傳送給第一個接聽的代理人。
    
      - 若要依次提供對每個代理程式的新呼叫，請按一下 [**迴圈**]。
    
      - 若要隨時以其在 [**代理程式**清單] 中列出的順序提供給 agent 的新呼叫，請按一下 [**串列**]。
    
      - 若要同時為登入 Lync Server 2013 和回應群組應用程式的所有代理提供新的呼叫，請按一下 [**助理**]。 已設定為 [代理程式] 的 Lync 2010 系統管理員可以查看所有等待的通話，並以任何順序接聽等待通話。 呼叫會傳送給接受該通話的第一份工程師，之後，其他 Lync 2010 連絡人使用者就不會再看到通話。

10. 在 [**代理**程式] 中，指定您要建立的代理清單的方式：
    
      - 若要使用自訂的代理清單，請按一下 [**定義自訂的代理群組**]，然後執行下列其中一項操作：
        
          - 若要將使用者新增到 [代理] 群組，請按一下 [**選取**]，然後在 [**選取代理**搜尋] 欄位中，輸入您要新增至此群組的所有或部分名稱，然後按一下 [**尋找**]。 在產生的代理清單中，按一下使用者，然後按一下 **[確定]**。
        
          - 若要從 [代理] 群組中移除使用者，請在 [代理程式清單] 中，按一下您要移除的使用者，然後按一下 [**移除**]。
        
          - 若要變更代理在使用迴圈路由或串列路由的群組中提供來電的順序，請在 [代理程式清單] 中，按一下使用者，然後按一下向上箭號或向下箭號。
    
      - 若要使用 Microsoft Exchange Server 通訊群組清單作為代理群組，請按一下 [**使用現有的電子郵件通訊群組清單**]，然後在 [**通訊群組清單位址**] 中，輸入通訊群組清單的電子郵件地址（例如，NetworkSupport@contoso.com）。
        
        如果您使用電子郵件通訊群組清單，您會受到下列限制：
        
          - 您無法針對 [代理] 群組選取多個通訊群組清單。 每個群組只支援單一通訊群組清單。
        
          - 如果通訊群組清單包含一或多個通訊群組清單，則嵌套通訊群組清單的成員不會新增到 [代理程式清單]。
        
          - 如果已選取 [串列或迴圈路由]，伺服器會根據路由方法及代理在通訊群組清單中的顯示順序，將來電提供給適當的代理程式。
        
          - 如果通訊群組清單中包含已啟用 Lync Server 2010 的使用者，但尚未啟用企業語音，則會將它們以 dysfunctional agent 的形式新增到 agent 群組中。 請確定通訊群組清單的所有成員都已針對其使用者帳戶啟用企業語音功能。
        
        <div>
        

        > [!IMPORTANT]  
        > 如果您使用電子郵件通訊群組清單，回應群組管理員或使用者可能會看到隱藏的成員資格或隱藏清單。

        
        </div>
        
        隱藏的成員資格或隱藏清單可能會變成可見，如下所示：
        
          - 如果已將通訊群組清單設定為隱藏成員資格，且回應群組管理員將通訊群組清單指派給 agent 清單，則使用者可以呼叫該群組來找出成員是誰。
        
          - 如果通訊群組清單已設定為在 Exchange 全域通訊清單中隱藏，回應群組管理員可能可以查看通訊群組清單，並將它指派給 agent 清單（如果回應群組進程具有適當的使用者權利），而且許可權，即使系統管理員沒有適當的使用者權利和許可權也一樣。

11. 按一下 [認可]****。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>使用 Windows PowerShell 來建立或修改代理群組

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  使用 [**新-CsRgsAgentGroup** ] 來建立新的代理群組。 使用 [**設定] CsRgsAgentGroup**修改現有的代理群組。 在命令列上執行：
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    例如：
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > Agent 警示時間設定不能超過180秒。 如果 agent 警示時間超過180秒，用戶端應用程式會拒絕呼叫，因為 SIP 事務計時器達到最大等待時間。

    
    </div>

4.  確認已建立 [代理] 群組。 用盡
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>請參閱


[刪除 Lync Server 2013 中的代理群組](lync-server-2013-delete-an-agent-group.md)  


[在 Lync Server 2013 中管理回應群組代理群組](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[新-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

