---
title: 編輯 Edge 設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 您可以透過設定下列屬性來編輯 Edge Server 或 Edge 集區的設定：
ms.openlocfilehash: b7784e15d7446a51dfa9aed03dd1154bba157485
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635327"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>編輯 Edge 設定展開工具 (適用於 Lync Server 2010)
 
您可以透過設定下列屬性來編輯 Edge Server 或 Edge 集區的設定： 
  
 **一般**
  
- **內部集區 FQDN**：內部集區完整功能變數名稱為 edge Server 或 edge 集區的身分識別，如網域名稱系統中所定義的 (DNS) 主機 (A 或 AAAA 為 IPv6) 記錄。
    
- 如果您想要啟用 Edge Server 或 Edge 集區以進行與其他會話初始通訊協定夥伴的同盟，請選取 [ **啟用此 Edge 集區的同盟 (埠 5061)** 。
    
    > [!IMPORTANT]
    > 您只能為同盟定義一部 Edge Server 或 Edge 集區。 關聯的螢幕擷取畫面所顯示的設定會指出已經為同盟設定其他 Edge Server 或 Edge 集區。 同盟 (_sipfederationtls ._tcp 的外部 DNS SRV 記錄。 \<external domain name\>) 會指向同盟的 Edge Server 或 Edge 集區。 
  
- 內部設定複寫 **埠 (HTTPS)**（預設在 TCP 埠4443上）是本機 (的埠，也就是對中央管理存放區) 副本的本機伺服器進行複製。 中央管理存放區的本機複本位於每一部電腦 SQL Server 的 **RTCLOCAL** 資料庫中。 複製是從中央管理伺服器 (，或是將中央管理伺服器角色) 至 Edge server 的前端伺服器或前端集區，也是一個內部介面埠。
    
  **下一個躍點選取範圍**
  
- 從清單中選取 [下一個躍點集區]。 您可以定義 Director、Director 集區、前端伺服器或前端集區，以承擔此角色。 下一個躍點集區是伺服器或伺服器集區，可接受來自 Edge Server 或 Edge 集區內部介面的輸入 SIP 訊息，並將輸出 SIP 傳送至 Edge internal interface。
    
    > [!NOTE]
    > Director 是選用的角色，如果您決定不部署 Director，則 (單一電腦或集區) 的前端伺服器會承擔 Director 角色。 
  
  **外部設定**
  
您可以在此區段的屬性中編輯 Edge Server 或 Edge 集區的外部設定屬性。 您可以編輯下列內容：
  
- 如果您想要將獨特的 IP 位址和完整功能變數名稱指派給每個 Edge Server 服務，請選取 [ **為 web 會議和 A/V 啟用個別 FQDN 和 IP 位址** ] 核取方塊。
    
    > [!NOTE]
    > 如果選擇不選取核取方塊，則必須為每個 Edge Service 使用不同的連接埠。 每個 Edge service 會共用針對 Access Edge service 定義的 FQDN，因此會使用相同的 IP 位址。 每個 Edge 服務必須由不同的 IP 位址搭配相同的連接埠，或相同的 IP 位址搭配唯一的連接埠值唯一識別。 
  
- 如果您想要將 A/V Edge service 設定為使用專用位址或其他在網路位址轉譯 (NAT) 裝置後隱藏的其他位址，請選取 [ **A/V Edge service 為 NAT** ]。
    
- 若要編輯 **Access edge service**，請定義 access edge Service 的 **集區 FQDN** （如 DNS 中所定義的主機 (A）和 AAAA （如果) 記錄和埠值使用 IPv6）
    
- 若要編輯 **Web 會議 edge service**，請定義 Web 會議 edge Service 的 **集區 FQDN** （如 DNS 中所定義的主機 (a）和 AAAA （如果) 記錄及埠值使用 IPv6）。
    
- 若要編輯 **A/V Edge service**，請依主機 (A 定義 A/V Edge Service 的 **集區 FQDN** ，以及在) 記錄及埠值時使用 IPv6 時 AAAA。
    
    > [!IMPORTANT]
    > 如果您已選取 [ **為 web 會議和 A/V 啟用個別 FQDN 和 IP 位址** ] 核取方塊，則只有 Access Edge service 集區 FQDN 可供編輯。 請為這三個 Edge Service 各自指派不同的連接埠。
  
  **確定**：接受並認可對話方塊的變更。
  
  **取消**：捨棄變更，並關閉對話方塊。
  
  **說明**：顯示此說明畫面。
  

