---
title: 編輯 Edge 設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 您可以設定下列屬性來編輯 Edge 伺服器或 Edge 池的設定：
ms.openlocfilehash: 78edbc8093b54474ac9f0429b5232851a5a16663
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697378"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>編輯 Edge 設定展開工具 (適用於 Lync Server 2010)
 
您可以設定下列屬性來編輯 Edge 伺服器或 Edge 池的設定： 
  
 **一般**
  
- **內部池 FQDN**：內部池的完整功能變數名稱是 edge 伺服器或 edge 池的身分識別，如在網域名稱系統（DNS）主機（A 或 AAAA IPv6）記錄中定義。
    
- 如果您想要將 Edge 伺服器或 Edge 池與其他會話初始通訊協定夥伴啟用聯盟，請選取 **[針對此 Edge 池啟用同盟（埠5061）** ]。
    
    > [!IMPORTANT]
    > 您只能針對同盟定義一台邊緣伺服器或邊緣池。 相關聯的螢幕擷取畫面中所顯示的設定會指出已針對同盟設定其他邊緣伺服器或邊緣池。 同盟（_sipfederationtls _tcp 的外部 DNS SRV 記錄。\<外部功能變數名稱\>）會指向 [聯盟] 的邊緣伺服器或邊緣池。 
  
- 預設情況下，**內部配置複製埠（HTTPS）** 是在 TCP 埠4443上，會複製中央管理儲存區的本機（也就是本機的邊緣伺服器）複本。 中央管理存放區的本機複本位於每一部電腦上的 SQL Server **RTCLOCAL**資料庫中。 從中央管理伺服器（或擁有中央管理伺服器角色的前端伺服器或前端池）開始，到邊緣伺服器且是內部介面埠，複製是單向的。
    
  **下一個躍點選取**
  
- 選取您**下一個躍點數池**的清單。 您可以定義 Director、主管池、前端伺服器或前端池來擔當此角色。 下一個躍點池是伺服器或伺服器池，可接受來自 Edge 伺服器或 Edge 池內部介面的入站 SIP 訊息，並將輸出 SIP 傳送到 Edge 內部介面。
    
    > [!NOTE]
    > 主管是一個選用的角色，如果您決定不部署控制器，前端伺服器（單一電腦或池中）會假設主管角色。 
  
  **外部設定**
  
此區段的屬性可讓您編輯 Edge 伺服器或 Edge 池外部設定的屬性。 下列屬性可供編輯：
  
- 如果您想要為每個 Edge 伺服器服務指派不同的 IP 位址及完整的功能變數名稱，請選取 [**針對 web 會議與 A/V 啟用個別的 FQDN 和 IP 位址**] 核取方塊。
    
    > [!NOTE]
    > 如果您選擇不選取此核取方塊，則必須針對每個 Edge 服務使用不同的埠。 每個 Edge 服務都會共用為存取邊緣服務定義的 FQDN，因此會使用相同的 IP 位址。 每個 Edge 服務必須由不同的 IP 位址和相同的埠，或是相同的 IP 位址和唯一的埠值來唯一識別。 
  
- 如果您想要將 A/V Edge 服務設定為使用私人位址或其他將隱藏在網路位址轉譯（NAT）裝置後面的位址，請選取**a/v 邊緣服務**。
    
- 若要編輯**存取邊緣服務**，請根據主機（A 和 AAAA If 使用 IPv6）中定義的存取邊緣服務定義**池 FQDN** ，並將埠值
    
- 若要編輯**網路會議 edge 服務**，請根據主機（a 和 AAAA if IPv6）中的定義，為網路會議 edge 服務定義一個**池 FQDN** （a），並使用埠值
    
- 若要編輯**a/v 邊緣服務**，請根據主機（a 和 AAAA If 使用 IPv6）的定義，為 a/v edge 服務定義一個**池 FQDN** （a），以及一個埠值
    
    > [!IMPORTANT]
    > 如果您已選取 [**啟用 web 會議的個別 FQDN 和 IP 位址] 和 [A/V** ] 核取方塊，則只有存取邊緣服務池 FQDN 可供編輯。 為三個邊緣服務中的每一個指派不同的埠。
  
  **確定**：接受並認可對話方塊的變更。
  
  **取消**：捨棄變更，並關閉對話方塊。
  
  **說明**：顯示此說明畫面。
  

