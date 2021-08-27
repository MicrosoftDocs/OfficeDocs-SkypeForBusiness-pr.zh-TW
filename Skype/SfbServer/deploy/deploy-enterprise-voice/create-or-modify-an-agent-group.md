---
title: 在商務用 Skype 中建立或修改代理人群組
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: 在 [回應群組] 的 [商務用 Skype Server 企業語音中建立或修改代理程式群組。
ms.openlocfilehash: 367e8e752042d7b8585fdae918f747aa77085223
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589015"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>在商務用 Skype 中建立或修改代理人群組
 
在 [回應群組] 的 [商務用 Skype Server 企業語音中建立或修改代理程式群組。
  
當您建立代理群組時，需要選取指派給該群組的代理，並指定額外的群組設定，例如路由方法以及代理是否可以登入和登出群組。 
  
必須登入和登出群組的代理程式（與登入或商務用 Skype 外的登入）稱為正式代理程式。 正式代理必須先登入此群組，才可以接聽路由傳送到此群組的電話。 對於以兼職身分接聽群組來電的代理而言，這可能相當實用。 正式代理程式可以按一下商務用 Skype 中的功能表項目，以開啟 Windows Internet Explorer internet 瀏覽器，並顯示網頁主控台，以登入和登出其群組。
  
未登入或登出群組的代理人稱為「非正式代理人」。 非正式代理程式會在登入商務用 Skype 時自動登入群組，而且無法登出群組。
  
只有內部部署的使用者可以成為代理人。如果將代理人從內部部署移至線上，回應群組電話將無法路由傳送給該代理人。
  
使用下列其中一個程式來建立或修改代理程式群組。
  
> [!IMPORTANT]
> 當您將使用者指派為回應群組代理人時，如果他們已啟用隱私權模式，請通知他們需要搜尋 "RGS Presence Watcher" 連絡人並將他們新增到其連絡人清單。已啟用隱私權模式但其連絡人清單中沒有 "RGS Presence Watcher" 的代理人，無法接收到打給回應群組的電話。未啟用隱私權模式的代理人則不受影響。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>使用商務用 Skype Server 控制台建立或修改代理程式群組

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。
    
    > [!NOTE]
    > 如果您是受管理工作流程的其中一位委派回應群組管理員，您可以在您管理的工作流程中建立群組並加以使用。 
  
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。  
    
3. 在左側導覽列中，按一下 **[回應群組]**，然後按一下 **[群組]**。
    
4. 在 [ **群組** ] 頁面上，執行下列其中一項操作：
    
   - 若要建立新的代理人群組，請按一下 [ **新增**]。 在 [ **選取服務** ] 搜尋欄位中，輸入您要在其中新增群組之 **ApplicationServer** 服務的全部或部分名稱。 在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。
    
   - 若要修改現有的代理人群組，請在 [搜尋] 欄位中輸入 agent 群組的全部或部分名稱。 在產生的清單中，按一下您想要的群組，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。
    
5. 在 [ **名稱**] 中，輸入代理人群組的識別名稱。
    
6. 在 **[描述]** 中，輸入群組的描述。
    
7. 在 **[參與原則]** 中，選取下列其中一項作業來設定群組的登入行為：
    
   - 選取 **[非正式]** 指定群組中的專員不需要登入及登出群組。 當代理人登入商務用 Skype 時，會自動登入群組。
    
   - 選取 **[正式]** 指定群組中的專員必須登入和登出群組。 當您選取此選項時，代理程式會按一下商務用 Skype 中的功能表項目，以開啟 Internet Explorer，並顯示網頁主控台以供登入和登出群組。
    
8. 在 **[警示時間 (秒)]** 中，指定專員的電話響幾秒 (預設值為 20 秒) 後會轉給下一個線上專員。
    
    > [!IMPORTANT]
    > 「代理程式警示時間」設定不得超過180秒。 如果代理程式警示時間超過180秒，用戶端應用程式會拒絕呼叫，因為 SIP 交易計時器已達到其最長等待時間。 
  
9. 在 **[路由方法]** 中，選取將電話路由轉送給群組專員的方式，如下所示：
    
   - 若 **要在已** 閒置最長 (商務用 Skype 最長 **) 的情況** 下提供新來電，請按一下 [最 **長閒置**]。 
    
   - 若要將新電話同時提供給所有的線上專員，請按一下 **[平行]**。該電話會路由傳送給第一個接聽的專員。
    
   - 若要將新電話輪流提供給每個專員，請按一下 **[循環配置資源]**。 
    
   - 若要永遠依照 **[專員]** 清單中的順序將新的來電提供給專員，請按一下 **[序列]**。 
    
   - 若要同時針對登入商務用 Skype 和回應群組應用程式的所有代理商進行呼叫，不論其目前目前狀態為何，**請按一下 [** 語音應答]。 設定為代理人的使用者可以查看所有等待的來電，並以任何順序接聽等候通話。 通話會傳送給第一個接受此通話的代理商，在此之後，其他代理程式就不再看到通話。
    
10. 在 [ **代理人**] 中，指定您要如何建立代理人清單：
    
    - 若要使用自訂的代理人清單，請按一下 [ **定義代理人的自訂群組**]，然後執行下列其中一項操作：
    
    - 若要將使用者新增至代理人群組，請按一下 [ **選取**]，然後在 [ **選取代理** 搜尋] 欄位中，輸入您要新增至此群組的使用者名稱全部或部分名稱，然後按一下 [ **尋找**]。 在產生的代理程式清單中，按一下使用者，然後按一下 **[確定]**。
    
    - 若要從代理人群組中移除使用者，請在代理程式清單中，按一下您要移除的使用者，然後按一下 [ **移除**]。
    
    - 若要變更代理程式在使用迴圈傳送或串列路由的群組中提供通話的順序，請在代理程式清單中，按一下使用者，然後按一下向上鍵或向下箭號。 
    
    - 若要使用 Microsoft Exchange Server 通訊群組清單作為代理人群組，請按一下 [**使用現有的電子郵件通訊群組清單**]，然後在 [**通訊群組清單位址**] 中，輸入通訊群組清單的電子郵件地址 (例如，NetworkSupport@contoso.com) 。
    
      如果您使用電子郵件通訊群組清單，您會受到下列限制：
    
      - 您無法為專員群組選取多個通訊群組清單。每一個群組只支援一個通訊群組清單。
    
      - 如果通訊群組清單包含一或多個通訊群組清單，則巢狀通訊群組清單的成員不會加入到專員清單中。
    
      - 如果選取了串列或迴圈複用路由，則伺服器會根據路由方法以及代理列在通訊群組清單中的順序，向適當的代理人提供來電。
    
      - 如果通訊群組清單包含的使用者已啟用 Lync Server 2010，但未啟用企業語音，則它們會以 dysfunctional 代理程式的形式新增至代理人群組。 請確定通訊群組清單的所有成員都已針對其使用者帳戶啟用企業語音。
    
    > [!IMPORTANT]
    > 如果您使用電子郵件通訊群組清單，回應群組管理員或使用者可能會看到隱藏的成員資格或隱藏的清單。 
  
    在下列情況下，隱藏的成員資格或隱藏的清單會顯現出來：
    
     - 如果已設定通訊群組清單以便隱藏成員資格，且回應群組管理員將通訊群組清單指派給代理人清單，則使用者可以呼叫群組以找出成員是誰。 
    
     - 如果已設定通訊群組清單，使其在 Exchange 全域通訊清單中隱藏，回應群組管理員可能會看到通訊群組清單，並將其指派給代理人清單，如果回應群組處理具有適當的使用者權限，即使系統管理員沒有適當的使用者權限。
    
11. 按一下 **[認可]**。
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>使用商務用 Skype Server 管理命令介面建立或修改代理程式群組

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 使用 **New-CsRgsAgentGroup** 建立新的代理人群組。 使用 **get-csrgsagentgroup** 來修改現有的代理人群組。 在命令列中執行：
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    例如：
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > 「代理程式警示時間」設定不得超過180秒。 如果代理程式警示時間大於180秒，用戶端應用程式會拒絕呼叫，因為 SIP 交易計時器已達到其最長等待時間。 
  
4. 確認已建立代理人群組。 執行：
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>另請參閱

[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)
  
[New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Get-csrgsagentgroup](/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)