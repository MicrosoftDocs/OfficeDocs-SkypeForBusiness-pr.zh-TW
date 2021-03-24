---
title: 在商務用 Skype Server 2015 中編輯拓撲
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 在完成最初的面試問題之後，您可以編輯該網站的 (FQDN) 和 IP 位址的完整功能變數名稱。 若要這麼做，請在 [全域拓撲] 頁面上，連按兩下您要編輯的網站。
ms.openlocfilehash: 9a345c753195c32907d078d5ee4a267b8b96d6b0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093181"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="78345-104">在商務用 Skype Server 2015 中編輯拓撲</span><span class="sxs-lookup"><span data-stu-id="78345-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="78345-105">在完成最初的面試問題之後，您可以編輯該網站的 (FQDN) 和 IP 位址的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="78345-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="78345-106">若要這麼做，請在 **[全域拓撲]** 頁面上，連按兩下您要編輯的網站。</span><span class="sxs-lookup"><span data-stu-id="78345-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="78345-107">規劃工具會顯示所選網站的網站拓撲。</span><span class="sxs-lookup"><span data-stu-id="78345-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="78345-108">在網站頁面的底部有四個索引標籤：</span><span class="sxs-lookup"><span data-stu-id="78345-108">At the bottom of the site page are four tabs:</span></span>

![規劃工具網站拓撲](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="78345-110">網站拓撲-目前顯示的頁面，如建議使用拓撲的視覺概況。</span><span class="sxs-lookup"><span data-stu-id="78345-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="78345-111">Edge Network 圖表-Edge Network 框圖頁面是設計人員在規劃工具中大部分工作的地方。</span><span class="sxs-lookup"><span data-stu-id="78345-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="78345-112">此圖表顯示建議的商務用 Skype Server 2015 拓撲的網路設定，以及伺服器、集區的可編輯專案，以及硬體和網域名稱系統 (DNS) 負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="78345-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="78345-113">Edge 管理報告-Edge 系統管理員報告總共包含四個報告：</span><span class="sxs-lookup"><span data-stu-id="78345-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![Edge 管理報告頁面](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="78345-115">摘要報告-Edge 網路設定的一般設定報告。</span><span class="sxs-lookup"><span data-stu-id="78345-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="78345-116">如果您將 [ **Edge Network 圖表** ] 頁面上的值編輯為 [拓撲 TCP/IP，並將用於實際部署中的 FQDN 值，則會在此顯示這些位址和名稱。</span><span class="sxs-lookup"><span data-stu-id="78345-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="78345-117">否則，會顯示預設文字。</span><span class="sxs-lookup"><span data-stu-id="78345-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="78345-118">憑證報告-憑證報告會列出拓撲所需憑證的主體名稱和主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="78345-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="78345-119">防火牆報告-防火牆報告會列出在基礎結構中設定周邊防火牆所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="78345-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="78345-120">這包括 IP 位址 (預設或編輯的值) 、伺服器角色、來源 IP 及埠、目的地 IP 及埠、傳輸通訊協定、應用程式通訊協定，以及相關的附注。</span><span class="sxs-lookup"><span data-stu-id="78345-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="78345-121">DNS 報告-DNS 報告會列出您必須建立之 DNS 專案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="78345-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="78345-122">包含正常運作所需的記錄類型、FQDN、IP 位址和註解。</span><span class="sxs-lookup"><span data-stu-id="78345-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="78345-123">網站摘要-網站摘要會顯示您透過回答最初的面試問題或填入 **設計網站** 中的值所做的選擇。</span><span class="sxs-lookup"><span data-stu-id="78345-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="78345-124">也會呈現容量資訊。</span><span class="sxs-lookup"><span data-stu-id="78345-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78345-125">[網站摘要] 頁面上的資訊是針對各項設計所自訂的，無法包含此處詳述的所有區段或資訊。</span><span class="sxs-lookup"><span data-stu-id="78345-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="78345-126">編輯網路設定圖表</span><span class="sxs-lookup"><span data-stu-id="78345-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="78345-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="78345-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="78345-128">在商務用 Skype Server 2015 規劃工具中，設計人員大部分的工作，都是由為網狀圖上專案的 IP 位址和完整功能變數名稱定義 (Fqdn) 所組成。</span><span class="sxs-lookup"><span data-stu-id="78345-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="78345-129">在此頁面上輸入的資訊會包含在規劃工具中的報告及其他資訊中。</span><span class="sxs-lookup"><span data-stu-id="78345-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![規劃工具的網狀圖表](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="78345-131">規劃工具會以預設的 IP 位址和 Fqdn 來建立網狀圖表和預設文字。</span><span class="sxs-lookup"><span data-stu-id="78345-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="78345-132">若要編輯網路圖和輸入值：</span><span class="sxs-lookup"><span data-stu-id="78345-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="78345-133">選擇要開始處理的網路區段。</span><span class="sxs-lookup"><span data-stu-id="78345-133">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="78345-134">例如，按兩下文字 **access1.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="78345-134">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="78345-135">在開啟的對話方塊中，輸入伺服器 access1.contoso.com 的實際 FQDN 和實際的 IP 位址，取代131.107.155.3。</span><span class="sxs-lookup"><span data-stu-id="78345-135">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="78345-136">按一下 **[確定]** 儲存項目。</span><span class="sxs-lookup"><span data-stu-id="78345-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="78345-137">繼續編輯 IP 位址和 FQDN，提供各硬體負載平衡器的虛擬 IP 位址，或集區中各伺服器的網域名稱系統 (DNS) 負載平衡的伺服器項目。</span><span class="sxs-lookup"><span data-stu-id="78345-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="78345-p111">規劃工具的一項實用功能在於可以漸進地指派 IP 位址範圍和伺服器主機名稱，而不需要設計師分別編輯集區中的每部伺服器。例如：</span><span class="sxs-lookup"><span data-stu-id="78345-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="78345-140">按兩下集區化的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="78345-140">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="78345-141">當對話方塊開啟時，選取 **[您要使用 IP 和 FQDN 作為此叢集中所有同等級伺服器的起點嗎?]**。</span><span class="sxs-lookup"><span data-stu-id="78345-141">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="78345-142">例如，第一部伺服器的開始值是 fe0101.contoso.com 和192.168.21.122 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="78345-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="78345-143">在 [ **前端伺服器 FQDN**] 中輸入 fe0.contoso.com，在 **前端伺服器的 IP 位址** 中輸入192.168.21.131，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="78345-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="78345-144">自動遞增值功能會將集區中的所有伺服器更新為 fe01 到 fe06，並將所有 IP 位址從192.168.21.131 更新為136。</span><span class="sxs-lookup"><span data-stu-id="78345-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="78345-145">完成所有編輯之後，請完成下列步驟以儲存拓撲：</span><span class="sxs-lookup"><span data-stu-id="78345-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="78345-146">若要儲存規劃工具設計，請 **按一下 [** 檔案]，然後按一下 [ **儲存拓撲** ] 或 [ **另存拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="78345-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="78345-147">如果出現 **[另存規劃工具]** 對話方塊，請在 **[檔案名稱]** 中輸入檔案的名稱，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="78345-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="78345-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="78345-148">See also</span></span>
<span data-ttu-id="78345-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="78345-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="78345-150">編輯設計</span><span class="sxs-lookup"><span data-stu-id="78345-150">Editing the Design</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)