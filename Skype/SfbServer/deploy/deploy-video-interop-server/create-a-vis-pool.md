---
title: 在商務用 Skype Server 中建立 VIS 集區
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 摘要：使用拓撲產生器在商務用 Skype Server 中建立影片 Interop 伺服器集區。
---

# <a name="create-a-vis-pool-in-skype-for-business-server"></a>在商務用 Skype Server 中建立 VIS 集區
 
**總結：** 使用拓撲產生器在商務用 Skype Server 中建立影片 Interop 伺服器集區。
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>使用拓撲產生器建立 VIS 或 VIS 集區

1. 在前端伺服器上開啟拓撲產生器。 在 [拓撲產生器] 的左窗格中，以滑鼠右鍵按一下 [ **影片 Interop 伺服器** 集區]，然後選擇 [ **新增影片 interop 伺服器集** 區] 
    
2. 這會開啟 [ **建立新的視頻 Interop 伺服器集** 區] 嚮導。 提供新的視頻 Interop 伺服器的集區 FQDN，然後選取 [ **此集區擁有一個伺服器** ] 或 [ **此集區擁有多部伺服器** （根據您的需求）]，然後按 **[下一步]**。
    
    如果您想要部署 Video Interop 伺服器集區以提供高可用性，請選取 [ **此集區擁有多部伺服器**]。 使用此選項時，請記住下列事項： 
    
    - 您必須部署 DNS 負載平衡以支援視頻 Interop 伺服器集區。 
    
   - 在下一個頁面上，針對 [ **定義此集區中的電腦** ] 專案中，將集區中每一部伺服器的 **電腦 FQDN** 輸入文字欄位，然後按一下 [ **新增**]。 重複此步驟，將另一個視頻 Interop 伺服器新增至集區。 定義集區中的所有電腦後，按 **[下一步]**。
    
     如果您只想要在集區中部署一個視頻 Interop 伺服器，因為您不需要高可用性，請選取 [ **此集區擁有一部伺服器** ]，然後按 **[下一步]**。
    
3. 從下拉式清單中選取 [下一個躍點集區/FE]，然後按 **[下一步]**。
    
4. 選取要與 VIS 建立關聯的 Edge 集區，然後按下 **[完成]**。
    
5. 設定 TCP 或 TLS 埠。
    
    從拓撲產生器的左窗格中選取新加入的視頻 Interop 伺服器，以滑鼠右鍵按一下，然後選擇 [ **編輯屬性**]。 根據您的需求啟用或更新 TCP 或 TLS 埠，然後選擇 **[確定]**。 雖然新增了預設 TLS，但只有 TCP 已透過 Cisco 整合通訊管理員 (CallManager 或 CUCM) 進行完整測試。
    
6. 新增影片閘道。 若要執行此動作，請展開 [共用元件]，以滑鼠右鍵按一下 [**影片閘道**]，然後選取 [**新增 vcd**
    
7. 提供視頻閘道 FQDN 或 IP 位址。 影片閘道可能位於子域或不同的網域中。 您系統的 VTCs 所使用的 CUCM 會用作影片閘道。
    
8. 視需要選取 [IPv4] 或 [IPv6]。 您可以使用所有設定的 IP 位址，或將服務使用方式限制為選取的 IP 位址。
    
9. 選取視頻閘道的聆聽埠。 選取傳輸通訊協定 (TCP 或 TLS) ，並將其與設定為影片 SIP 主幹的視頻 Interop 伺服器建立關聯。 視頻閘道的傳輸通訊協定應符合為 VIS 設定的傳輸通訊協定。
    
10. 在上述步驟完成之後，會新增相對應的 SIP 影片主幹。 以滑鼠右鍵按一下 SIP 影片主幹，然後選取剛新增的主幹。 影片的 SIP 主幹名稱、關聯的視頻 Interop 伺服器、SIP 傳輸通訊協定和埠均可全部變更。 
    
    > [!NOTE]
    >  影片 Interop 伺服器支援1： N 主幹。 因此可以新增多個主幹，這與單一的視頻 Interop 伺服器相關聯，每個主幹會在不同的視頻閘道上終止。 這種限制是，特定的視頻閘道具有一個且只有一個主幹可定義給商務用 Skype Server 部署。
  
11. 依照在[商務用 Skype Server 2015 中建立及發行新拓撲中](../../deploy/install/create-and-publish-new-topology.md)所述的方式，發佈拓撲檔。
    
    > [!NOTE]
    > 若要改善復原能力，您可能想要設定第二個視頻 Interop 伺服器或 VIS 集區，或是備份前端集區。 如需詳細資訊，請參閱 [恢復機制](../../plan-your-deployment/video-interop-server.md#resiliency) 。
  
現在，使用拓撲產生器執行的所有工作都是完整的。 繼續在新的 VIS 伺服器或伺服器上安裝軟體。
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中部署 VIS 伺服器角色](deploy-the-vis-server-role.md)

[在商務用 Skype Server 中規劃視頻 Interop 伺服器](../../plan-your-deployment/video-interop-server.md)
  
[在商務用 Skype Server 2015 中建立及發行新的拓撲](../../deploy/install/create-and-publish-new-topology.md)
