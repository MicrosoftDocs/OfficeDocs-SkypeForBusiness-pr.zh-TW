---
title: 在商務用 Skype Server 2015 中編輯拓撲
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: 在完成最初的面試問題之後，您可以編輯該網站的 (FQDN) 和 IP 位址的完整功能變數名稱。 若要這麼做，請在 [全域拓撲] 頁面上，連按兩下您要編輯的網站。
ms.openlocfilehash: 2276f2959329c77744054976e3a49f5ad72778ae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776163"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中編輯拓撲

在完成最初的面試問題之後，您可以編輯該網站的 (FQDN) 和 IP 位址的完整功能變數名稱。 若要這麼做，請在 **[全域拓撲]** 頁面上，連按兩下您要編輯的網站。

規劃工具會顯示所選網站的網站拓撲。 在網站頁面的底部有四個索引標籤：

![規劃工具網站拓撲。](../../media/Planning_Tool_Site_Topology.png)

- 網站拓撲-目前顯示的頁面，如建議使用拓撲的視覺概況。

- Edge Network 圖表-Edge Network 框圖頁面是設計人員在規劃工具中大部分工作的地方。 此圖表顯示建議的商務用 Skype Server 2015 拓撲的網路設定，其中包含伺服器、集區的 IP 位址和 fqdn 的可編輯專案，以及硬體和網域名稱系統 (DNS) 負載平衡器。

- Edge 管理報告-Edge 系統管理員報告總共包含四個報告：

     ![Edge 管理報告頁面。](../../media/Planning_Tool_Summary_Report.png)

  - 摘要報告-Edge 網路設定的一般設定報告。 如果您將 [ **Edge Network 圖表** ] 頁面上的值編輯為 [拓撲 TCP/IP，並將用於實際部署中的 FQDN 值，則會在此顯示這些位址和名稱。 否則，會顯示預設文字。

  - 憑證報告-憑證報告會列出拓撲所需憑證的主體名稱和主體替代名稱。

  - 防火牆報告-防火牆報告會列出在基礎結構中設定周邊防火牆所需的資訊。 這包括 IP 位址 (預設或編輯的值) 、伺服器角色、來源 IP 及埠、目的地 IP 及埠、傳輸通訊協定、應用程式通訊協定，以及相關的附注。

  - DNS 報告-DNS 報告會列出您必須建立之 DNS 專案的相關資訊。 包含正常運作所需的記錄類型、FQDN、IP 位址和註解。

- 網站摘要-網站摘要會顯示您透過回答最初的面試問題或填入 **設計網站** 中的值所做的選擇。 也會呈現容量資訊。

    > [!NOTE]
    > [網站摘要] 頁面上的資訊是針對各項設計所自訂的，無法包含此處詳述的所有區段或資訊。

## <a name="edit-the-network-configuration-diagram"></a>編輯網路設定圖表
<a name="Edit_Network_diagram"> </a>

在商務用 Skype Server 2015 規劃工具中，設計人員大部分的工作，都是由為網狀圖上專案的 IP 位址和完整功能變數名稱定義 (fqdn) 所組成。 在此頁面上輸入的資訊會包含在規劃工具中的報告及其他資訊中。

![規劃工具的網狀圖表。](../../media/Planning_Tool_Network_Diagram.png)

規劃工具會以預設的 IP 位址和 Fqdn 來建立網狀圖表和預設文字。

若要編輯網路圖和輸入值：

1. 選擇要開始處理的網路區段。 例如，按兩下文字 **access1.contoso.com**。 在開啟的對話方塊中，輸入伺服器 access1.contoso.com 的實際 FQDN 和實際的 IP 位址，取代131.107.155.3。

2. 按一下 **[確定]** 儲存項目。

3. 繼續編輯 IP 位址和 FQDN，提供各硬體負載平衡器的虛擬 IP 位址，或集區中各伺服器的網域名稱系統 (DNS) 負載平衡的伺服器項目。

規劃工具的一項實用功能在於可以漸進地指派 IP 位址範圍和伺服器主機名稱，而不需要設計師分別編輯集區中的每部伺服器。例如：

1. 按兩下集區化的前端伺服器。 當對話方塊開啟時，選取 **[您要使用 IP 和 FQDN 作為此叢集中所有同等級伺服器的起點嗎?]**。

2. 例如，第一部伺服器的開始值是 fe0101.contoso.com 和192.168.21.122 的 IP 位址。

3. 在 [ **前端伺服器 FQDN**] 中輸入 fe0.contoso.com，在 **前端伺服器的 IP 位址** 中輸入192.168.21.131，然後按一下 **[確定]**。

4. 自動遞增值功能會將集區中的所有伺服器更新為 fe01 到 fe06，並將所有 IP 位址從192.168.21.131 更新為136。

完成所有編輯之後，請完成下列步驟以儲存拓撲：

若要儲存規劃工具設計，請 **按一下 [** 檔案]，然後按一下 [ **儲存拓撲** ] 或 [ **另存拓撲**]。 如果出現 **[另存規劃工具]** 對話方塊，請在 **[檔案名稱]** 中輸入檔案的名稱，然後按一下 **[儲存]**。

## <a name="see-also"></a>另請參閱
<a name="Edit_Network_diagram"> </a>

[編輯設計](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)