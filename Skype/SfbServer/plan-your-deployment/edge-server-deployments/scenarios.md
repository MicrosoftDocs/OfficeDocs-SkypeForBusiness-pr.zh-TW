---
title: 商務用 Skype Server 中的邊緣伺服器案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 摘要：請查看這些案例，協助您規劃商務用 Skype Server 中的邊緣伺服器拓撲。
ms.openlocfilehash: 64d38b5c9b4a32991bf87bd6ba8af87c92db115f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754163"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>商務用 Skype Server 中的邊緣伺服器案例
 
**摘要：** 請複習這些案例，協助您規劃商務用 Skype Server 中的邊緣伺服器拓撲。
  
我們有一些案例圖表，可協助在您想要實施哪種商務用 Skype Server Edge 伺服器拓撲中進行視覺化和決定。 挑選好的候選方案之後，您就可以開始瞭解您需要解決的環境需求。 下列是適用于任何案例，因此我們先將它提及。
  
這些數位僅針對範例所示（也就是包含範例 IPv4 與 IPv6 資料），不代表實際的通訊流程，而是您可能的流量的高層次視圖。 您也可以在下列每個案例的埠圖表中看到埠詳細資料。
  
圖表會針對內部介面與 .net （也就是樣本圖）顯示 .com;當然，當您要將自己的最終邊緣方案放在一起時，您自己的專案可能會有很大的差異。
  
在任何圖表中，我們不會包含主管（這是一個選用元件），但您可以單獨閱讀此資訊（在其他規劃主題中提到）。
  
如前所述，圖表中有範例 IPv6 資料。 在[商務用 Skype server 中規劃 Edge 伺服器部署](edge-server-deployments.md)的大部分檔將會參照 IPv4，但如果您想要使用 IPv6，您肯定會受到支援。 請注意，您在指派的位址空間中需要 IPv6 位址，而且它們必須與 IPv4 Ip 一樣使用內部和外部定址。 您可以在 Windows 中使用雙堆疊功能，這是適用于 IPv4 和 IPv6 的獨立且獨特的網路堆疊。 如果您需要的話，這會讓您同時指派 IPv4 與 IPv6 位址。
  
NAT 裝置允許使用 NAT64 （IPv6 到 IPv4）與 NAT66 （IPv6 到 IPv6）），而且這對搭配商務用 Skype Server 而言是有效的。
  
> [!IMPORTANT]
> 如果您使用的是「通話許可控制」（CAC），則必須在內部介面上使用 IPv4 才能運作。 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>單一整合的商務用 Skype Server Edge 伺服器（含私人 IP 位址和 NAT）

在這個案例中，沒有高可用性的選項。 這將意味著您在硬體上的花費較少，且部署更簡單。 如果必須具備高可用性，請參閱下方的伸縮合併案例。
  
![使用 NAT 的單一綜合邊緣與專用 IP 的邊緣案例](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>埠圖表

我們也為單一整合邊緣伺服器的埠建立圖表。
  
![Edge 案例的網路周長單一合併邊緣](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>單一整合的商務用 Skype Server Edge 伺服器與公用 IP 位址

在這個案例中，沒有高可用性的選項。 這將意味著您在硬體上的花費較少，且部署更簡單。 如果必須具備高可用性，請參閱下方的伸縮合併案例。
  
![含公用 IP 的單一合併邊緣的邊緣案例](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>埠圖表

我們也為單一整合邊緣伺服器的埠建立圖表。
  
![Edge 案例的網路周長單一合併邊緣](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>已調整整合的商務用 Skype Server Edge 池（含 DNS 負載平衡），以及私人 IP 位址和 NAT

在這種情況下，您可以在 Edge 部署中取得高可用性，這可讓您有伸縮性和容錯移轉支援的優點。
  
![使用 NAT 調整合並邊緣的邊緣案例、含專用 IP 的 DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>埠圖表

我們也有一個使用 DNS 負載平衡來調整整合的邊緣池的圖表。
  
![邊緣案例的網路周邊使用 DNS LB 調整合並的邊緣](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>使用 DNS 負載平衡與公用 IP 位址調整整合的商務用 Skype Server Edge 池

在這種情況下，您可以在 Edge 部署中取得高可用性，這可讓您有伸縮性和容錯移轉支援的優點。
  
![已調整合並邊緣的邊緣案例，具有公用 IP 的 DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>埠圖表

我們也有一個使用 DNS 負載平衡來調整整合的邊緣池的圖表。
  
![邊緣案例的網路周邊使用 DNS LB 調整合並的邊緣](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>已調整整合的商務用 Skype Server Edge 池（含硬體負載平衡）

在這種情況下，您可以在 Edge 部署中取得高可用性，這可讓您有伸縮性和容錯移轉支援的優點。
  
![使用 HLB 調整合並邊緣的邊緣案例](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
