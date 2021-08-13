---
title: 設定商務用 Skype Server 中的 Office Web 應用程式伺服器的整合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 摘要：閱讀此主題以瞭解如何設定 Office web Apps Server 與商務用 Skype Server 之間的整合，以啟用 Web 會議的 PowerPoint 簡報。
ms.openlocfilehash: abaf430ffd2f426d8ed4821409691cc140bb9fa8fe3dd0e23bcf10cbc444c33b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338781"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>設定商務用 Skype Server 中的 Office Web 應用程式伺服器的整合
 
**摘要：** 閱讀此主題以瞭解如何設定 Office web Apps Server 與商務用 Skype Server 之間的整合，以啟用 Web 會議的 PowerPoint 簡報。
  
商務用 Skype Server 採用 Office web Apps Server 來處理 web 會議的 PowerPoint 簡報。 如需此方法之優點的詳細資訊，請參閱[在商務用 Skype Server 中規劃會議](../../plan-your-deployment/conferencing/conferencing.md)。
  
在您設定商務用 Skype Server 以使用 Office 網頁應用程式伺服器之前，您必須確定已部署並設定 Office Web apps server。 如需 Office Web Apps Server 的詳細資訊，請參閱[部署基礎結構的文章： Office Online Server](/webappsserver/deploy-the-infrastructure-office-web-apps-server)。 
  
成功安裝 Office web 應用程式伺服器並正確設定網頁伺服器陣列之後，您必須將 Office Web Apps Server 探索 URL 新增至商務用 Skype Server 拓撲，才能設定商務用 Skype Server 與新伺服器通訊。 
  
> [!NOTE]
> Office Web Apps Server 的最新小小 Office Online Server 稱為「商務用 Skype Server 支援的]。 如需詳細資訊，請參閱[Office Online Server 檔](/officeonlineserver/office-online-server)。 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>設定商務用 Skype Server 與 Office Web Apps Server 通訊

若要將 Office Web Apps Server 新增至拓撲，請完成下列步驟：
  
1. 開啟商務用 Skype Server 拓撲產生器。
    
2. 在 **[拓撲產生器]** 對話方塊中，選取 **[從現有的部署下載拓撲]**，然後按一下 **[確定]**。
    
3. 在 **[另存拓撲]** 對話方塊的 **[檔案名稱]** 方塊中，鍵入拓撲文件的名稱 (例如 **PreWebAppsServerTopology**)，然後按一下 **[儲存]**。如果新拓撲之後發生問題，就可以擷取並重新發行此拓撲。
    
4. 在 [拓撲產生器] 中，展開 [**商務用 Skype Server**]，展開您網站的名稱，然後展開 [ **Enterprise Edition 前端** 集區]，以滑鼠右鍵按一下其中一個集區的名稱，然後按一下 [**編輯屬性**]。
    
5. 在 **[編輯內容]** 對話方塊的 **[一般]** 索引標籤上，尋找標題 **[關聯 Office Web Apps Server]**，然後按一下 **[新增]** (或從下拉式清單中選取現有的 Office Web Apps Server)。
    
6. 在 **[定義新的 Office Web Apps Server]** 對話方塊的 **[Office Web Apps Server FQDN]** 方塊中，鍵入 Office Web Apps Server 電腦的完整網域名稱 (FQDN)；執行此動作時，您的 Office Web Apps Server 探索 URL 應自動輸入至 **[Office Web Apps Server 探索 URL]** 方塊。
    
   - 如果 Office web apps server 安裝在內部部署上，且位於與商務用 Skype Server 相同的網路區域中，則 **Office Web apps server 的選項會部署在外部網路 (也就是，不應該選取周邊/網際網路)** 。
    
   - 如果 Office Web Apps Server 部署在內部防火牆外，則選取 **[Office Web Apps Server 部署在外部網路 (亦即周邊/網際網路]** 選項。
    
7. 在 **[定義新的 Office Web Apps Server]** 對話方塊中，按一下 **[確定]**，然後按一下 **[編輯內容]** 對話方塊中的 **[確定]**。 然後會將探索 URL 列為集區的關聯之一。
    
您必須對每個需要與 Office Web Apps Server 建立關聯的集區重複此程序。
  
將探索 URL 新增至拓撲之後，您必須發佈更新的拓撲。 在拓撲產生器中執行此作業的步驟如下：
  
1. 按一下 **[動作]**，然後按一下 **[發行拓撲]**。
    
2. 在發行拓撲精靈的 **[發行拓撲]** 頁面上，按 **[下一步]**。
    
3. 在 **[發行精靈完成]** 頁面上，按一下 **[完成]**。
    
4. 關閉拓撲產生器。
    
## <a name="configure-access-for-external-users"></a>設定外部使用者的存取權

如果您想要讓外部使用者 (也就是說，使用者從組織的防火牆外登入) 若要存取 Office 網頁應用程式伺服器 PowerPoint 簡報，則您將需要使用 Office web apps server 和反向 proxy 伺服器。 您也必須建立及設定網站發行規則，這會協助確保使用者能夠連接到伺服器。 
  
## <a name="validate-the-configuration"></a>驗證設定

Office Web Apps Server 新增至拓撲之後，在發行拓撲之後，您應該會在商務用 Skype Server 事件記錄檔中看到兩個新的事件記錄事件。 首先，應新增 LS 資料 MCU 事件 (事件識別碼 41034) 。此事件會報告已發現 Office Web Apps Server：
  
 **已探索 web 會議服務器 Office 的 web 應用程式伺服器，PowerPoint 內容已啟用。**
  
除了該之外，您還應該看到另一個 LS 資料 MCU 事件 (事件識別碼 41032) 會傳回 Office Web Apps Server URLs。 例如，您應該會看到類似下列的內容：
  
 **web 會議服務器 Office web Apps server discovery 已成功。**
  
 **OfficeWeb 應用程式伺服器內部簡報者頁面： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ; 嵌入 =**
  
 **OfficeWeb 應用程式伺服器內部出席者頁面： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ; 嵌入 = true&amp;=**
  
如果您已設定外部使用者的存取權，您也會看到類似下列專案的內容：
  
 **OfficeWeb Apps Server 外部簡報者頁面： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ; 嵌入**
  
 **OfficeWeb 應用程式伺服器內部出席者頁面： <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> ;**
  
如果您看到 LS 資料 MCU 事件（事件識別碼為41033），表示 Office Web Apps Server discovery 失敗。 在此情況下，商務用 Skype Server 會根據需要嘗試許多次數，以探索新設定的 Office Web Apps Server。 如果探索過程重複失敗，您應該移除拓撲檔中 Office 的 web 應用程式伺服器、發佈更新的拓撲，然後在解決連線問題後，嘗試將 Office Web 應用程式伺服器新增回拓撲。
  
如果 Office 網頁應用程式伺服器似乎已正確設定，且已被探索程式辨識，您可以在一對商務用 Skype 用戶端間共用 PowerPoint 簡報，以確認 Office 網頁應用程式伺服器的運作如期運作。 如果使用者 A 可以載入及顯示 PowerPoint 簡報，而且如果使用者 B 可以加入會議，並查看該簡報，則 Office Web Apps Server 仍在運作中。
  
即使 Office 網頁應用程式伺服器似乎已正確設定，當您嘗試共用 PowerPoint 簡報時，可能會收到錯誤訊息「某些共用功能因伺服器連線問題而無法使用」。 如果您收到該錯誤訊息，您應該重新開機前端伺服器 (或與新 Office Web Apps server 關聯的伺服器) 。
