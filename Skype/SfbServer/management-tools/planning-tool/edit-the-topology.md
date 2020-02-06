---
title: 在商務用 Skype Server 2015 中編輯拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: 完成最初的訪談問題之後，您可以編輯該網站的完整功能變數名稱（FQDN）和 IP 位址。 若要這樣做，請在 [全域拓撲] 頁面上，按兩下您要編輯的網站。
ms.openlocfilehash: dae99620f34b832dd4abe0baf83d6df11b388750
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816442"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中編輯拓撲

完成最初的訪談問題之後，您可以編輯該網站的完整功能變數名稱（FQDN）和 IP 位址。 若要這樣做，請在 [**全域拓撲**] 頁面上，按兩下您要編輯的網站。

規劃工具會顯示所選網站的網站拓撲。 [網站] 頁面底部有四個索引標籤：

![規劃工具的站台拓撲](../../media/Planning_Tool_Site_Topology.png)

- [網站拓撲]-目前顯示的頁面，上面有拓撲的視覺概況，如建議使用。

- [邊緣網狀圖]-[邊緣網狀圖] 頁面是設計工具在規劃工具中的大部分工作位置。 圖表會顯示建議的商務用 Skype Server 2015 拓朴的網路設定，以及伺服器、池以及硬體和網域名稱系統（DNS）負載平衡器的可編輯專案。

- Edge 管理員報告-Edge 管理員報告總共包含四個報告：

     ![Edge 管理員報告頁面](../../media/Planning_Tool_Summary_Report.png)

  - 摘要報告-邊緣網路設定的一般設定報告。 如果您將 [ **Edge 網狀圖**] 頁面上的值編輯為要在實際部署中使用的 [拓撲 tcp/ip] 和 [FQDN] 值，這些位址和名稱將會顯示在這裡。 否則，會出現預設文字。

  - 憑證報告-證書報告將會列出拓朴所需之憑證的主旨名稱和消費者替代名稱。

  - 防火牆報告-防火牆報告會列出在基礎結構中設定週邊防火牆所需的資訊。 這包括 IP 位址（預設或已編輯的值）、伺服器角色、來源 IP 和埠、目的地 IP 與埠、傳輸通訊協定、應用程式協定，以及相關的筆記。

  - DNS 報告-DNS 報告會列出您必須建立之 DNS 專案的相關資訊。 包括適當作業所需的記錄類型、FQDN、IP 位址和批註。

- [網站摘要]： [網站摘要] 會顯示您在回答最初的面試問題或填入 [**設計網站**] 中的值時所做的選項。 也會顯示容量資訊。

    > [!NOTE]
    > [網站摘要] 頁面上的資訊會針對每個設計進行自訂，並且可能不會包含所有章節或本文中的詳細資訊。

## <a name="edit-the-network-configuration-diagram"></a>編輯網路設定圖表
<a name="Edit_Network_diagram"> </a>

在商務用 Skype Server 2015 規劃工具中，設計工具的大部分工作，都是為 [網狀圖] 上的專案定義 IP 位址和完整功能變數名稱（Fqdn）的專案。 在此頁面上輸入的資訊會納入至 [規劃工具] 中所含的報告及其他資訊。

![規劃工具的網路圖表](../../media/Planning_Tool_Network_Diagram.png)

規劃工具會建立含 IP 位址和 Fqdn 預設文字的網狀圖表。

若要編輯 network 圖表及輸入值：

1. 選擇要開始使用的網路區段。 例如，按兩下文字 [ **access1.contoso.com**]。 在開啟的對話方塊中，輸入 [伺服器 access1.contoso.com] 的實際 FQDN，以及實際的 IP 位址（取代131.107.155.3）。

2. 按一下 **[確定]** 儲存專案。

3. 繼續編輯 IP 位址和 Fqdn，提供硬體負載平衡器的虛擬 IP 位址或網域名稱系統（DNS）的伺服器專案在池中的伺服器負載平衡。

規劃工具有一個實用的功能，就是它可以逐漸指派 IP 位址和伺服器主機名稱的範圍，而不需要設計者在池中編輯每個獨立的伺服器。 例如：

1. 按兩下共端的前端伺服器。 對話方塊開啟時，請選取 [**您想要將 IPs 和 FQDN 作為此群集中所有等價伺服器的起始點嗎？**]。

2. 例如，第一個伺服器的起始值是 fe0101.contoso.com，IP 位址是192.168.21.122。

3. 在 [**前端伺服器 FQDN**] 中輸入 fe0.contoso.com，在**前端伺服器 IP 位址**中輸入192.168.21.131，然後按一下 **[確定]**。

4. [自動遞增值] 功能會將池中的所有伺服器更新為 fe01 到 fe06，並將所有 IP 位址從192.168.21.131 移至136。

完成所有編輯之後，請完成下列步驟以儲存拓朴：

若要儲存規劃工具設計，請**按一下 [** 檔案]，然後按一下 [**儲存拓撲**] 或 [**另存拓撲為**]。 如果出現 [**儲存規劃工具**] 對話方塊，請在 [**檔案名**] 中輸入檔案名，然後按一下 [**儲存**]。

## <a name="see-also"></a>另請參閱
<a name="Edit_Network_diagram"> </a>

[編輯設計](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
