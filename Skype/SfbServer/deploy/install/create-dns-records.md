---
title: 建立 商務用 Skype Server 的 DNS 記錄
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: 摘要：瞭解如何設定 DNS 並建立 DNS 記錄以安裝商務用 Skype Server。
ms.openlocfilehash: 5e974df94aba8b879c672250b69432dfd0a5f1f3
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860534"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>建立 商務用 Skype Server 的 DNS 記錄
 
**總結：** 瞭解如何設定 DNS 並建立 DNS 記錄以安裝商務用 Skype Server。
  
若要讓商務用 Skype Server正常運作，必須備妥一些網域名稱系統 (DNS) 設定。 這可讓用戶端知道如何存取服務，以及讓伺服器彼此瞭解。 每個部署只需要完成這些設定一次，因為一旦您指派 DNS 專案，它就可以在整個網域中使用。 您可以依任何循序執行步驟 1 到 5。 不過，您必須依序執行步驟 6、7 和 8，以及步驟 1 到 5 之後，如圖表中所述。 建立 DNS 記錄包含步驟 8 的步驟 5。 如需規劃 DNS 的詳細資訊，請參閱[商務用 Skype Server 的環境](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)需求或[2019 商務用 Skype Server伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。
  
> [!IMPORTANT]
> 請務必注意，這只是如何在 Windows Server DNS 環境中建立 DNS 記錄的範例。 商務用 Skype Server需要許多其他 DNS 專案，而建立 DNS 記錄的程式取決於您用來管理組織中 DNS 的系統。 如需 DNS 需求的完整清單，請參閱[商務用 Skype Server 的 DNS 需求](../../plan-your-deployment/network-requirements/dns.md)。 
  
![概觀圖表。](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>設定 DNS

需要有 DNS 記錄，商務用 Skype Server才能正常運作，且可供使用者存取。
  
此範例使用名為 pool.contoso.local 的 DNS 負載平衡 FQDN。 此集區是由執行 商務用 Skype Server Enterprise Edition 的三部伺服器所組成。 Standard Edition前端伺服器只能包含單一伺服器。 藉由使用Standard Edition，在參考前端角色時，您只會使用單一Standard Edition伺服器的完整功能變數名稱 (FQDN) ，而不是建立伺服器的 DNS 負載平衡集區，如本範例所示。 這個僅使用前端角色的簡單範例包含下表中的 DNS 專案。 若要規劃您的特定 DNS 需求，請參閱[商務用 Skype Server的 DNS 需求](../../plan-your-deployment/network-requirements/dns.md)。 
  
 
|**描述**|**記錄類型**|**名稱**|**解析為**|**負載平衡類型**|
|:-----|:-----|:-----|:-----|:-----|
|內部 Web 服務 FQDN  <br/> |A  <br/> |webint.contoso.local  <br/> |內部 Web 服務的 VIP  <br/> |支援的軟體和硬體  <br/> |
|集區 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |伺服器 SFB01 的 IP 位址  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |伺服器 SFB01 的 IP 位址  <br/> |DNS  <br/> |
|集區 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |伺服器 SFB02 的 IP 位址  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |伺服器 SFB02 的 IP 位址  <br/> |DNS  <br/> |
|集區 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |伺服器 SFB03 的 IP 位址  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |伺服器 SFB03 的 IP 位址  <br/> |DNS  <br/> |
|商務用 Skype自動探索  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |內部 Web 服務的 VIP  <br/> |支援的軟體和硬體  <br/> |
|會議簡易 URL  <br/> |A  <br/> |meet.contoso.local  <br/> |內部 Web 服務的 VIP  <br/> |支援的軟體和硬體  <br/> |
|撥入簡易 URL  <br/> |A  <br/> |dialin.contoso.local  <br/> |內部 Web 服務的 VIP  <br/> |支援的軟體和硬體  <br/> |
|Web 排程器簡單 URL  <br/> |A  <br/> |scheduler.contoso.local  <br/> |內部 Web 服務的 VIP  <br/> |支援的軟體和硬體  <br/> |
|系統管理簡單 URL  <br/> |A  <br/> |admin.contoso.local  <br/> |內部 Web 服務的 VIP  <br/> |支援的軟體和硬體  <br/> |
|舊版探索  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |集區 FQDN (埠 5061)   <br/> |不適用  <br/> |
   
### <a name="create-dns-records"></a>建立 DNS 記錄

1. 登入 DNS 伺服器，然後開 **啟 伺服器管理員**。
    
2. 按一下 [ **工具** ] 下拉式功能表，然後按一下 **[DNS]**。
    
3. 在 SIP 網域的主控台樹中，展開 [**正向對應區域**]，然後展開將安裝商務用 Skype Server的 SIP 網域。
    
4. 以滑鼠右鍵按一下 SIP 網域，然後選 **取 [新增主機 (A 或 AAAA)**]，如圖所示。
    
     ![選取新的 A 記錄。](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. 在 [ **名稱]** 方塊中，輸入主機記錄的名稱 (功能變數名稱會自動附加) 。
    
6. 在 [ **IP 位址] 方** 塊中，輸入個別前端伺服器的 IP 位址，然後選 **取 [建立相關聯的指標 (PTR) 記錄** ] 或 [如果適用， **允許任何已驗證的使用者以相同的擁有者名稱更新 DNS 記錄]**。 請注意，這會假設使用 DNS 來平衡所有流量的負載，但 Web 服務除外。 在此範例中，我們有三部前端伺服器，如表格所示。
    
   |**伺服器名稱**|**類型**|**資料**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |主機 (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |主機 (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |主機 (A)  <br/> |10.0.0.7  <br/> |
   
7. 接下來，建立集區的 DNS 負載平衡專案。 DNS 負載平衡可讓 DNS 在使用相同的 DNS 集區名稱時，將要求傳送至集區中的個別伺服器。 如需 DNS 和負載平衡的詳細資訊，請參閱[商務用 Skype Server的 DNS 需求](../../plan-your-deployment/network-requirements/dns.md)。 
    
    > [!NOTE]
    > 將多部伺服器集區在一起，僅適用于Enterprise Edition部署。 如果您要部署單一Enterprise伺服器或Standard Edition伺服器，則只需要為單一伺服器建立 A 記錄。 
  
    例如，如果您有名為 pool.contoso.local 的集區和三部前端伺服器，您會建立下列 DNS 專案：
    
   |**FQDN**|**類型**|**資料**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |主機 (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |主機 (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |主機 (A)  <br/> |10.0.0.7  <br/> |
   
8. 繼續為計畫部署中的所有伺服器建立 A 記錄。 
    
9. 若要建立服務記錄 (SRV) 記錄以進行舊版探索，請以滑鼠右鍵按一下 SIP 網域，然後選取 [ **其他新記錄]**。
    
10. 在 **[選取資源記錄類型**] 中，按一下 **[服務位置 (SRV)**]，然後按一下 [ **建立記錄]**。
    
11. 按一下 **[服務**]，然後輸入 **_sipinternaltls**。
    
12. 按一下 [通訊 **協定**]，然後輸入 **_tcp**。
    
13. 按一下 **[埠號碼]**，然後輸入 **5061**。
    
14. 按一下 **[提供此服務的主機**]，然後輸入集區或Standard Edition伺服器的 FQDN。
    
     ![[新增資源記錄] 對話方塊的螢幕擷取畫面。](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. 按一下 **[確定**]，然後按一下 [ **完成]**。
    
### <a name="verify-dns-records"></a>確認 DNS 記錄

1. 使用屬於已驗證使用者群組成員或具有對等許可權的帳戶，登入網域中的用戶端電腦。
    
2. 按一下 **[開始**]，然後輸入 **cmd**，然後按 Enter。
    
3. 輸入 **nslookup \<FQDN of the Front End pool\>** 或 **\<FQDN of the Standard Edition server or single Enterprise Edition server\>** ，然後按 Enter。
    
4. 繼續驗證部署的其餘 A 記錄。
    
5. 如果您支援舊版用戶端並建立 SRV 記錄，請在 **nslookup** 提示字元中輸入 **set type=srv** 來進行驗證，然後按 Enter。
    
6. 輸入 **_sipinternaltls._tcp。 *域*** 例如， (_sipinternaltls._tcp.contoso.local) ，然後按 Enter 鍵。
    
7. 預期的輸出應該類似圖中所示的輸出。 請注意，並非所有 DNS 記錄都會顯示在範例輸出中，但應驗證所有記錄。 
    
     ![確認 dns 設定。](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

