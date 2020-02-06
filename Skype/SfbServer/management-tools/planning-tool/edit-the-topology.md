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
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="a1296-104">在商務用 Skype Server 2015 中編輯拓撲</span><span class="sxs-lookup"><span data-stu-id="a1296-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="a1296-105">完成最初的訪談問題之後，您可以編輯該網站的完整功能變數名稱（FQDN）和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a1296-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="a1296-106">若要這樣做，請在 [**全域拓撲**] 頁面上，按兩下您要編輯的網站。</span><span class="sxs-lookup"><span data-stu-id="a1296-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="a1296-107">規劃工具會顯示所選網站的網站拓撲。</span><span class="sxs-lookup"><span data-stu-id="a1296-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="a1296-108">[網站] 頁面底部有四個索引標籤：</span><span class="sxs-lookup"><span data-stu-id="a1296-108">At the bottom of the site page are four tabs:</span></span>

![規劃工具的站台拓撲](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="a1296-110">[網站拓撲]-目前顯示的頁面，上面有拓撲的視覺概況，如建議使用。</span><span class="sxs-lookup"><span data-stu-id="a1296-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="a1296-111">[邊緣網狀圖]-[邊緣網狀圖] 頁面是設計工具在規劃工具中的大部分工作位置。</span><span class="sxs-lookup"><span data-stu-id="a1296-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="a1296-112">圖表會顯示建議的商務用 Skype Server 2015 拓朴的網路設定，以及伺服器、池以及硬體和網域名稱系統（DNS）負載平衡器的可編輯專案。</span><span class="sxs-lookup"><span data-stu-id="a1296-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="a1296-113">Edge 管理員報告-Edge 管理員報告總共包含四個報告：</span><span class="sxs-lookup"><span data-stu-id="a1296-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![Edge 管理員報告頁面](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="a1296-115">摘要報告-邊緣網路設定的一般設定報告。</span><span class="sxs-lookup"><span data-stu-id="a1296-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="a1296-116">如果您將 [ **Edge 網狀圖**] 頁面上的值編輯為要在實際部署中使用的 [拓撲 tcp/ip] 和 [FQDN] 值，這些位址和名稱將會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="a1296-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="a1296-117">否則，會出現預設文字。</span><span class="sxs-lookup"><span data-stu-id="a1296-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="a1296-118">憑證報告-證書報告將會列出拓朴所需之憑證的主旨名稱和消費者替代名稱。</span><span class="sxs-lookup"><span data-stu-id="a1296-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="a1296-119">防火牆報告-防火牆報告會列出在基礎結構中設定週邊防火牆所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="a1296-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="a1296-120">這包括 IP 位址（預設或已編輯的值）、伺服器角色、來源 IP 和埠、目的地 IP 與埠、傳輸通訊協定、應用程式協定，以及相關的筆記。</span><span class="sxs-lookup"><span data-stu-id="a1296-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="a1296-121">DNS 報告-DNS 報告會列出您必須建立之 DNS 專案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a1296-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="a1296-122">包括適當作業所需的記錄類型、FQDN、IP 位址和批註。</span><span class="sxs-lookup"><span data-stu-id="a1296-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="a1296-123">[網站摘要]： [網站摘要] 會顯示您在回答最初的面試問題或填入 [**設計網站**] 中的值時所做的選項。</span><span class="sxs-lookup"><span data-stu-id="a1296-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="a1296-124">也會顯示容量資訊。</span><span class="sxs-lookup"><span data-stu-id="a1296-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a1296-125">[網站摘要] 頁面上的資訊會針對每個設計進行自訂，並且可能不會包含所有章節或本文中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a1296-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="a1296-126">編輯網路設定圖表</span><span class="sxs-lookup"><span data-stu-id="a1296-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="a1296-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="a1296-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="a1296-128">在商務用 Skype Server 2015 規劃工具中，設計工具的大部分工作，都是為 [網狀圖] 上的專案定義 IP 位址和完整功能變數名稱（Fqdn）的專案。</span><span class="sxs-lookup"><span data-stu-id="a1296-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="a1296-129">在此頁面上輸入的資訊會納入至 [規劃工具] 中所含的報告及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="a1296-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![規劃工具的網路圖表](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="a1296-131">規劃工具會建立含 IP 位址和 Fqdn 預設文字的網狀圖表。</span><span class="sxs-lookup"><span data-stu-id="a1296-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="a1296-132">若要編輯 network 圖表及輸入值：</span><span class="sxs-lookup"><span data-stu-id="a1296-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="a1296-133">選擇要開始使用的網路區段。</span><span class="sxs-lookup"><span data-stu-id="a1296-133">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="a1296-134">例如，按兩下文字 [ **access1.contoso.com**]。</span><span class="sxs-lookup"><span data-stu-id="a1296-134">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="a1296-135">在開啟的對話方塊中，輸入 [伺服器 access1.contoso.com] 的實際 FQDN，以及實際的 IP 位址（取代131.107.155.3）。</span><span class="sxs-lookup"><span data-stu-id="a1296-135">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="a1296-136">按一下 **[確定]** 儲存專案。</span><span class="sxs-lookup"><span data-stu-id="a1296-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="a1296-137">繼續編輯 IP 位址和 Fqdn，提供硬體負載平衡器的虛擬 IP 位址或網域名稱系統（DNS）的伺服器專案在池中的伺服器負載平衡。</span><span class="sxs-lookup"><span data-stu-id="a1296-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="a1296-138">規劃工具有一個實用的功能，就是它可以逐漸指派 IP 位址和伺服器主機名稱的範圍，而不需要設計者在池中編輯每個獨立的伺服器。</span><span class="sxs-lookup"><span data-stu-id="a1296-138">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool.</span></span> <span data-ttu-id="a1296-139">例如：</span><span class="sxs-lookup"><span data-stu-id="a1296-139">For example:</span></span>

1. <span data-ttu-id="a1296-140">按兩下共端的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="a1296-140">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="a1296-141">對話方塊開啟時，請選取 [**您想要將 IPs 和 FQDN 作為此群集中所有等價伺服器的起始點嗎？**]。</span><span class="sxs-lookup"><span data-stu-id="a1296-141">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="a1296-142">例如，第一個伺服器的起始值是 fe0101.contoso.com，IP 位址是192.168.21.122。</span><span class="sxs-lookup"><span data-stu-id="a1296-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="a1296-143">在 [**前端伺服器 FQDN**] 中輸入 fe0.contoso.com，在**前端伺服器 IP 位址**中輸入192.168.21.131，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a1296-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="a1296-144">[自動遞增值] 功能會將池中的所有伺服器更新為 fe01 到 fe06，並將所有 IP 位址從192.168.21.131 移至136。</span><span class="sxs-lookup"><span data-stu-id="a1296-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="a1296-145">完成所有編輯之後，請完成下列步驟以儲存拓朴：</span><span class="sxs-lookup"><span data-stu-id="a1296-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="a1296-146">若要儲存規劃工具設計，請**按一下 [** 檔案]，然後按一下 [**儲存拓撲**] 或 [**另存拓撲為**]。</span><span class="sxs-lookup"><span data-stu-id="a1296-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="a1296-147">如果出現 [**儲存規劃工具**] 對話方塊，請在 [**檔案名**] 中輸入檔案名，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a1296-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1296-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a1296-148">See also</span></span>
<span data-ttu-id="a1296-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="a1296-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="a1296-150">編輯設計</span><span class="sxs-lookup"><span data-stu-id="a1296-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
