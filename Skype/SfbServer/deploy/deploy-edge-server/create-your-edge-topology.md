---
title: 為商務用 Skype Server 建立 Edge 拓撲
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
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 摘要：瞭解如何在商務用 Skype Server 中建立、發佈和匯出 Edge Server 拓撲。
ms.openlocfilehash: da0ec9709f53e22122a911015e94484fc673c6741ba5122fa796e7dded0105b5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322465"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>為商務用 Skype Server 建立 Edge 拓撲
 
**摘要：** 瞭解如何在商務用 Skype Server 中建立、發佈和匯出 Edge Server 拓撲。
  
拓撲產生器是您用來建立 Edge Server 拓撲的工具，就像它用於商務用 Skype Server 的任何拓撲元件一樣。 在執行下列步驟之前，您必須先設定至少一個前端集區或 Standard Edition 伺服器。
  
本文包含下列主題：
  
- 建立 Edge Server 拓撲
    
- 發佈 Edge Server 拓撲
    
- 匯出 Edge Server 拓撲
    
  > [!NOTE]
  > 若要遵循下列步驟，您必須以下列網域群組成員的使用者身分登入下列網域伺服器： 
  
- RTCUniversalServerAdmins
    
- Domain Admins
    
## <a name="build-your-edge-server-topology"></a>建立 Edge Server 拓撲

第一個部署步驟是建立您的商務用 Skype Server Edge Server 拓撲，此拓撲是由下列三個選項之一所組成：
  
- 單一 Edge Server
    
-  (一或多部伺服器上的 DNS 負載平衡 Edge 集區) 
    
-  (一或多部伺服器的硬體負載平衡 Edge 集區) 
    
如果您不確定需要的專案，請在開始執行下列步驟之前，請先移至規劃檔。 否則，讓我們開始吧。
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>定義單一 Edge Server 的拓撲

1. 登入商務用 Skype Server Standard Edition 伺服器或商務用 Skype Server 前端集區。
    
2. 之後，請開啟 **商務用 Skype Server 拓撲** 產生器。
    
3. 在主控台樹中，展開您要部署 Edge Server 的網站。
    
4. 以滑鼠右鍵按一下 [ **edge** 集區]，然後按一下 [ **新增 edge 集** 區]。
    
5. 在 [**定義新的 Edge 集** 區] 畫面上，按一下 **[下一步]** 。
    
6. 在 [ **定義 edge 集區 FQDN** ] 畫面上，輸入要使用 Edge Server 的內部完整功能變數名稱 (FQDN) ，然後選取 [ **單一電腦集** 區]，完成後，按一下 **[下一步]** 。
    
7. 在 [ **選取功能** ] 畫面上，您可以選擇：
    
   - 您可能想要對 SIP 存取服務、商務用 Skype Server Web 會議服務及 A/V Edge service 使用相同的 FQDN 和 IP 位址。 如果是的話，您必須選擇 [ **使用單一 FQDN 和 IP 位址] 核取方塊** (，並記住以下的步驟 9) 
    
   - 如果您打算啟用同盟，請選擇 [ **啟用此 Edge 集區的同盟 (埠 5061)** ] 核取方塊。
    
8. 按一下 **[下一步]** 後，您會在 [ **IP 選項** ] 畫面上找到您自己。 選項如下：
    
   - 在內部介面上啟用 IPv4
    
   - 在內部介面上啟用 IPv6
    
   - 在外部介面上啟用 IPv4
    
   - 在外部介面上啟用 IPv6
    
   不管您是使用 IPv4 或 IPv6 位址，還是要在內部或外部于您的 Edge Server 上套用這些位址，這些位址都是非常明確的， (您必須記住此步驟 10) 。 您也可以選擇將 Edge Server 或 Edge 集區設定為使用網路位址轉譯 (NAT) 位址的外部 IP 位址。 您可以選擇 **此 Edge 集區的外部 IP 位址由 NAT 轉譯** ] 核取方塊來執行此動作。 準備好時，按 **[下一步]** 。
    
9. 在 [外部 Fqdn] 畫面上，您的選擇取決於您在步驟7中所做的選擇。
    
   - 如果您已勾選 [ **使用單一 FQDN 和 IP 位址** ] 核取方塊，您必須在 [ **SIP 存取** ] 方塊中輸入單一的外部 FQDN。 接著，您必須為每個 edge service 輸入不同的埠號碼，以允許所有 edge service 彼此獨立連接。 建議您在5061的 **SIP Access** edge service 中，使用 **Web 會議** Edge service 的444，以及 **A/V** Edge service 的443。 完成時，按 **[下一步]**。
    
   - 如果您未選取 [ **使用單一 FQDN 和 IP 位址** ] 核取方塊，則您現在必須為 **SIP Access** Edge service、 **Web 會議** Edge service 和 **A/V** Edge service 輸入三個外部 fqdn。 完成時，按 **[下一步]**。
    
10. 您現在已經位於 [ **定義內部 IP 位址** ] 畫面。 在這裡，您會根據您在步驟8中所做的選擇，在 [ **內部 IPv4 位址** ] 和 [ **內部 IPv6 位址** ] 文字方塊中輸入 Edge Server 的 IP 位址。 準備好時，按 **[下一步]** 。
    
11. 在 [ **定義外部 IP 位址** ] 畫面上，您可以根據您先前的選擇，使用一些選項：
    
    - 您可以針對所有服務使用單一 FQDN。 如果是的話，請輸入您的外部 IPv4 或 IPv6 位址 (您在 [ **SIP 存取** ] 文字方塊中使用) ，然後按 **[下一步]**。
    
    - 您可能已選擇為服務使用三個不同的 Fqdn 和 IP 位址。 如果是這種情況，請為 **SIP Access** Edge Service、 **Web 會議** Edge service 及 **A/V** Edge service 輸入您的外部 IPv4 或 IPv6 位址，然後按 **[下一步]**。
    
    > [!NOTE]
    > 如果您先前未選擇啟用和指派 IPv6 定址，您就不會看到此對話方塊。 這是正常的，請移至下一個步驟。 
  
12. 如果您選擇在步驟8中使用 NAT 回來，您現在會看到 [ **公用 IP 位址** ] textbox 的畫面。 您必須輸入您為 A/V Edge service 設定的公用 IPv4 和/或 IPv6 位址，才能由 NAT 轉譯。 然後按一下 **下一步**。
    
13. [下一屏向上] 是 **定義下一個躍點**。 在 [ **下一個躍點集區]** 方塊中，選取您的內部集區名稱，其可能是前端集區或獨立集區。 如果您的環境中有 Director，您應該選擇 Director。 然後按一下 **下一步**。
    
14. 在 [**建立前端** 集區] 畫面上，您必須指定一或多個要與此 Edge Server 產生關聯的內部集區（包括前端集區和 Standard Edition 伺服器）。 只需選擇您要使用此 Edge Server 與支援的外部使用者進行通訊的內部集區名稱。 按一下 **[下一步]**。
    
    > [!NOTE]
    > 請注意，請注意，如果您的內部集區或獨立伺服器已使用不同的商務用 Skype Server Edge Server，則其不能有多個關聯。 如果您選擇的內部集區或獨立伺服器在該情況下，您將會看到警告，告知您其他 Edge Server，您可以決定是否要繼續。 如果您要繼續進行這個新的關聯，其他 Edge Server 的連線將停止。 
  
15. 按一下下一個畫面上的 **[完成]** 。
    
16. 現在您將能夠發佈此更新的技術，並遵循部署 edge server 的[商務用 Skype Server 中](deploy-edge-servers.md)的指示，從這裡部署至 Edge Server。
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>定義 DNS 負載平衡 Edge Server 集區的拓撲

1. 登入商務用 Skype Server Standard Edition 伺服器或商務用 Skype Server 前端伺服器。
    
2. 之後，請開啟 **商務用 Skype Server 拓撲** 產生器。
    
3. 在主控台樹中，展開您要部署 Edge Server 的網站。
    
4. 以滑鼠右鍵按一下 [ **edge** 集區]，然後按一下 [ **新增 edge 集** 區]。
    
5. 在 [**定義新的 Edge 集** 區] 畫面上，按一下 **[下一步]** 。
    
6. 在 [ **定義 edge 集區 FQDN** ] 畫面上，輸入要使用 Edge 集區的內部完整功能變數名稱 (FQDN) ，然後選取 [多部 **電腦集** 區]，完成後，按一下 **[下一步]** 。
    
7. 在 [ **選取功能** ] 畫面上，您可以選擇：
    
    - 您可能想要對 SIP 存取服務、商務用 Skype Server Web 會議服務及 A/V Edge service 使用相同的 FQDN 和 IP 位址。 如果是的話，您必須選擇 [ **使用單一 FQDN 和 IP 位址] 核取方塊** (，並記住以下的步驟 9) 
    
    - 如果您打算啟用同盟，請選擇 [ **啟用此 Edge 集區的同盟 (埠 5061)** ] 核取方塊。
    
8. 按一下 **[下一步]** 後，您會在 [ **IP 選項** ] 畫面上找到您自己。 選項如下：
    
    - 在內部介面上啟用 IPv4
    
   - 在內部介面上啟用 IPv6
    
   - 在外部介面上啟用 IPv4
    
   - 在外部介面上啟用 IPv6
    
     不管您是使用 IPv4 或 IPv6 位址，還是要在內部或外部于您的 Edge Server 上套用這些位址，這些位址都有很好的自我說明 (您必須記住這一點，) 步驟11。 您也可以選擇將 Edge Server 或 Edge 集區設定為使用網路位址轉譯 (NAT) 位址的外部 IP 位址。 您可以選擇 **此 Edge 集區的外部 IP 位址由 NAT 轉譯** ] 核取方塊來執行此動作。 準備好時，按 **[下一步]** 。
    
9. 在 [外部 Fqdn] 畫面上，您的選擇取決於您在步驟7中所做的選擇。
    
   - 如果您已勾選 [ **使用單一 FQDN 和 IP 位址** ] 核取方塊，您必須在 [ **SIP 存取** ] 方塊中輸入單一的外部 FQDN。 接著，您必須為每個 edge service 輸入不同的埠號碼，以允許所有 edge service 彼此獨立連接。 建議您在5061的 **SIP Access** edge service 中，使用 **Web 會議** Edge service 的444，以及 **A/V** Edge service 的443。 完成時，按 **[下一步]**。
    
   - 如果您未選取 [ **使用單一 FQDN 和 IP 位址** ] 核取方塊，則您現在必須為 **SIP Access** Edge service、 **Web 會議** Edge service 和 **A/V** Edge service 輸入三個外部 fqdn。 完成時，按 **[下一步]**。
    
10. 現在您已到達 [ **定義此集區中的電腦** ] 畫面。 按一下 [新增] 按鈕。
    
11. 您現在已經位於 [ **定義內部 IP 位址** ] 畫面。 在這裡，您會根據您在步驟8中所做的選擇，在 [ **內部 IPv4 位址** ] 和 [ **內部 IPv6 位址** ] 文字方塊中輸入 Edge Server 的 IP 位址。 準備好時，按 **[下一步]** 。
    
12. 在 [ **定義外部 IP 位址** ] 畫面上，您可以根據您先前的選擇，使用一些選項：
    
    - 您可以針對所有服務使用單一 FQDN。 如果是的話，請輸入您的外部 IPv4 或 IPv6 位址 (您在 [ **SIP 存取** ] 文字方塊中使用) ，然後按 **[下一步]**。
    
    - 您可能已選擇為服務使用三個不同的 Fqdn 和 IP 位址。 如果是這種情況，請為 **SIP Access** Edge Service、 **Web 會議** Edge service 及 **A/V** Edge service 輸入您的外部 IPv4 或 IPv6 位址，然後按 **[下一步]**。
    
    > [!NOTE]
    > 如果您先前未選擇啟用和指派 IPv6 定址，您就不會看到此對話方塊。 這是正常的，請移至下一個步驟。 
  
13. 按一下 **[完成]**。 您剛才建立的 Edge Server 現在應該會列在 [ **定義此集區中的電腦** ] 對話方塊中。
    
14. 在 [ **定義此集區中的電腦** ] 畫面仍然開啟時，請再次按一下 [ **新增** ] 按鈕，然後重複步驟11到13，直到您已新增您要在此集區中使用的所有 Edge server 為止。 完成時，按 **[下一步]**。
    
15. 如果您選擇在步驟8中使用 NAT 回來，您現在會看到 [ **公用 IP 位址** ] textbox 的畫面。 您必須輸入您為 A/V Edge service 設定的公用 IPv4 和/或 IPv6 位址，才能由 NAT 轉譯。 然後按一下 **下一步**。
    
16. [下一屏向上] 是 **定義下一個躍點**。 在 [ **下一個躍點集區]** 方塊中，選取您的內部集區名稱，其可能是前端集區或獨立集區。 如果您的環境中有 Director，您應該選擇 Director。 然後按一下 **下一步**。
    
17. 在 [**建立前端** 集區] 畫面上，您必須指定一或多個要與此 Edge Server 產生關聯的內部集區（包括前端集區和 Standard Edition 集區）。 只需選擇您要使用此 Edge Server 與支援的外部使用者進行通訊的內部集區名稱。 按一下 **[下一步]**。
    
    > [!NOTE]
    > 請注意，請注意，如果您的內部集區或獨立伺服器已使用不同的商務用 Skype Server Edge Server，則其不能有多個關聯。 如果您選擇的內部集區或獨立伺服器在該情況下，您將會看到警告，告知您其他 Edge Server，您可以決定是否要繼續。 如果您要繼續進行這個新的關聯，其他 Edge Server 的連線將停止。 
  
18. 按一下下一個畫面上的 **[完成]** 。
    
19. 現在您將能夠發佈此更新的技術，並遵循部署 edge server 的[商務用 Skype Server 中](deploy-edge-servers.md)的指示，從這裡部署至 Edge Server。
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>定義硬體負載平衡 Edge Server 集區的拓撲

1. 登入商務用 Skype Server Standard Edition 伺服器或商務用 Skype Server 前端伺服器。
    
2. 之後，請開啟 **商務用 Skype Server 拓撲** 產生器。
    
3. 在主控台樹中，展開您要部署 Edge Server 的網站。
    
4. 以滑鼠右鍵按一下 [ **edge** 集區]，然後按一下 [ **新增 edge 集** 區]。
    
5. 在 [**定義新的 Edge 集** 區] 畫面上，按一下 **[下一步]** 。
    
6. 在 [ **定義 edge 集區 FQDN** ] 畫面上，輸入要使用 Edge 集區的內部完整功能變數名稱 (FQDN) ，然後選取 [多部 **電腦集** 區]，完成後，按一下 **[下一步]** 。
    
7. 在 [ **選取功能** ] 畫面上，您可以選擇：
    
   - 您可能想要對 SIP 存取服務、商務用 Skype Server Web 會議服務及 A/V Edge service 使用相同的 FQDN 和 IP 位址。 如果是的話，您必須選擇 [ **使用單一 FQDN 和 IP 位址] 核取方塊** (，並記住以下的步驟 9) 
    
   - 如果您打算啟用同盟，請選擇 [ **啟用此 Edge 集區的同盟 (埠 5061)** ] 核取方塊。
    
8. 按一下 **[下一步]** 後，您會在 [ **IP 選項** ] 畫面上找到您自己。 選項如下：
    
   - 在內部介面上啟用 IPv4
    
   - 在內部介面上啟用 IPv6
    
   - 在外部介面上啟用 IPv4
    
   - 在外部介面上啟用 IPv6
    
     不管您是使用 IPv4 或 IPv6 位址，還是要在內部或外部于您的 Edge Server 上套用這些位址，這些位址都有很好的自我說明 (您必須記住這一點，) 步驟11。
    
     > [!NOTE]
     > 與其他兩個拓撲選項不同的是，使用硬體負載平衡器時，您 **不能** 選取 [選項]。 **Edge 集區的外部 IP 位址是由 NAT 轉譯**。 這是 **不受支援** 的。
  
9. 在 [外部 Fqdn] 畫面上，您的選擇取決於您在步驟7中所做的選擇。
    
   - 如果您已勾選 [ **使用單一 FQDN 和 IP 位址** ] 核取方塊，您必須在 [ **SIP 存取** ] 方塊中輸入單一的外部 FQDN。 接著，您必須為每個 edge service 輸入不同的埠號碼，以允許所有 edge service 彼此獨立連接。 建議您在5061的 **SIP Access** edge service 中，使用 **Web 會議** Edge service 的444，以及 **A/V** Edge service 的443。 完成時，按 **[下一步]**。
    
   - 如果您未選取 [ **使用單一 FQDN 和 IP 位址** ] 核取方塊，則您現在必須為 **SIP Access** Edge service、 **Web 會議** Edge service 和 **A/V** Edge service 輸入三個外部 fqdn。 完成時，按 **[下一步]**。
    
10. 現在您已到達 [ **定義此集區中的電腦** ] 畫面。 按一下 [新增] 按鈕。
    
11. 您現在已經位於 [ **定義內部 IP 位址** ] 畫面。 在這裡，您會根據您在步驟8中所做的選擇，在 [ **內部 IPv4 位址** ] 和 [ **內部 IPv6 位址** ] 文字方塊中輸入 Edge Server 的 IP 位址。 準備好時，按 **[下一步]** 。
    
12. 在 [ **定義外部 IP 位址** ] 畫面上，您可以根據您先前的選擇，使用一些選項：
    
    - 您可以針對所有服務使用單一 FQDN。 如果是的話，請輸入您的外部 IPv4 或 IPv6 位址 (您在 [ **SIP 存取** ] 文字方塊中使用) ，然後按 **[下一步]**。
    
    - 您可能已選擇為服務使用三個不同的 Fqdn 和 IP 位址。 如果是這種情況，請為 **SIP Access** Edge Service、 **Web 會議** Edge service 及 **A/V** Edge service 輸入您的外部 IPv4 或 IPv6 位址，然後按 **[下一步]**。
    
    > [!NOTE]
    > 如果您先前未選擇啟用和指派 IPv6 定址，您就不會看到此對話方塊。 這是正常的，請移至下一個步驟。 
  
13. 按一下 **[完成]**。 您剛才建立的 Edge Server 現在應該會列在 [ **定義此集區中的電腦** ] 對話方塊中。
    
14. 在 [ **定義此集區中的電腦** ] 畫面仍然開啟時，請再次按一下 [ **新增** ] 按鈕，然後重複步驟11到13，直到您已新增您要在此集區中使用的所有 Edge server 為止。 完成時，按 **[下一步]**。
    
15. [下一屏向上] 是 **定義下一個躍點**。 在 [ **下一個躍點集區]** 方塊中，選取您的內部集區名稱，其可能是前端集區或獨立集區。 如果您的環境中有 Director，您應該選擇 Director。 然後按一下 **下一步**。
    
16. 在 [**建立前端** 集區] 畫面上，您必須指定一或多個要與此 Edge Server 產生關聯的內部集區（包括前端集區和 Standard Edition 集區）。 只需選擇您要使用此 Edge Server 與支援的外部使用者進行通訊的內部集區名稱。 按一下 **[下一步]**。
    
    > [!NOTE]
    > 請注意，請注意，如果您的內部集區或獨立伺服器已使用不同的商務用 Skype Server Edge Server，則其不能有多個關聯。 如果您選擇的內部集區或獨立伺服器在該情況下，您將會看到警告，告知您其他 Edge Server，您可以決定是否要繼續。 如果您要繼續進行這個新的關聯，其他 Edge Server 的連線將停止。 
  
17. 按一下下一個畫面上的 **[完成]** 。
    
18. 現在您將能夠發佈此更新的技術，並遵循部署 edge server 的[商務用 Skype Server 中](deploy-edge-servers.md)的指示，從這裡部署至 Edge Server。
    
## <a name="publish-your-edge-server-topology"></a>發佈 Edge Server 拓撲

當您完成上述步驟之後，就可以發佈這個新的拓撲，也可以將它匯出至您的商務用 Skype Server edge Server 或 Edge 集區。 請遵循下列步驟：
  
1. 啟動 **拓撲** 產生器 (（如果尚未從先前的程式) 啟動）。
    
2. 在 [**拓撲** 產生器] 的主控台樹中，以滑鼠右鍵按一下 [**商務用 Skype Server** 然後按一下 [**商務用 Skype Server 拓撲** 產生器]。
    
3. 在嚮導的 [ **歡迎** ] 頁面上，按 **[下一步]**。
    
4. 在 [ **建立其他資料庫** ] 頁面上，按 **[下一步]**。
    
5. 當狀態指出資料庫建立成功時，請執行下列操作：
    
    - 若要查看記錄檔，請按一下 [ **查看記錄** 檔]。
    
    - 按一下 **[完成]**，關閉精靈。
    
## <a name="export-your-edge-server-topology"></a>匯出 Edge Server 拓撲

若要順利部署，商務用 Skype Server 部署嚮導必須存取中央管理存放區資料。 對於您網域或樹系中的內部伺服器，這通常是直接的。 Edge Server 位於網域之外，因此必須手動將拓撲檔案匯出至 Edge Server 位置，通常是在實體媒體上。 這會透過 PowerShell: 執行這種匯出
  
1. 啟動 **商務用 Skype Server 管理命令** 介面。
    
2. 在 **商務用 Skype Server 管理命令** 介面中，執行下列命令：
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. 將匯出的檔案複製到外部媒體 (例如，您可以從 Edge Server 位置) 的 USB 磁片磁碟機或網路共用。
    

