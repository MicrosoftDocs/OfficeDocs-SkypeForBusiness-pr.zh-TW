---
title: Lync Server 2013：設定媒體埠範圍設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e13e491037346d9c3186a8f15aada949c46ac8df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502090"
---
# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="bfc26-102">在 Lync Server 2013 中設定媒體埠範圍設定</span><span class="sxs-lookup"><span data-stu-id="bfc26-102">Configuring media port range settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfc26-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="bfc26-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="bfc26-104">媒體連接埠設定會顯著地影響用戶端效能，而應加以設定。</span><span class="sxs-lookup"><span data-stu-id="bfc26-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="bfc26-105">您可以使用 Lync Server 管理命令介面來設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="bfc26-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="bfc26-106">媒體連接埠範圍設定</span><span class="sxs-lookup"><span data-stu-id="bfc26-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bfc26-107">設定</span><span class="sxs-lookup"><span data-stu-id="bfc26-107">Setting</span></span></th>
<th><span data-ttu-id="bfc26-108">描述</span><span class="sxs-lookup"><span data-stu-id="bfc26-108">Description</span></span></th>
<th><span data-ttu-id="bfc26-109">Lync Server 管理命令介面 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="bfc26-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="bfc26-110">Cmdlet 參數</span><span class="sxs-lookup"><span data-stu-id="bfc26-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfc26-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="bfc26-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="bfc26-p102">指定伺服器傳送的連接埠範圍是否應該供用戶端用於媒體和訊號。配合使用子機碼值 MinMediaPort 和 MaxMediaPort。</span><span class="sxs-lookup"><span data-stu-id="bfc26-p102">Specifies whether the port ranges sent by the server should be used by the client for media and signaling. Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="bfc26-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="bfc26-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="bfc26-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="bfc26-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfc26-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="bfc26-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="bfc26-p103">指定用於媒體的起始連接埠號碼。與 MaxMediaPort 合併使用可指定連接埠範圍。建議最小範圍為 40 個連接埠。</span><span class="sxs-lookup"><span data-stu-id="bfc26-p103">Specifies the starting port number to use for media. Combines with MaxMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="bfc26-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="bfc26-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="bfc26-121">ClientMediaPort (代表用於用戶端媒體的起始連接埠號碼)</span><span class="sxs-lookup"><span data-stu-id="bfc26-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfc26-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="bfc26-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="bfc26-p104">指定用於媒體的最高連接埠號碼。與 MinMediaPort 合併使用可指定連接埠範圍。建議最小範圍為 40 個連接埠。</span><span class="sxs-lookup"><span data-stu-id="bfc26-p104">Specifies the highest port number to use for media. Combines with MinMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="bfc26-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="bfc26-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="bfc26-127">ClientMediaPortRange (表示可供用戶端媒體使用的連接埠總數；預設值為 40)</span><span class="sxs-lookup"><span data-stu-id="bfc26-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="bfc26-128">設定媒體連接埠範圍設定</span><span class="sxs-lookup"><span data-stu-id="bfc26-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="bfc26-129">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="bfc26-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bfc26-130">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="bfc26-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="bfc26-131">此 Cmdlet 傳回會議設定。</span><span class="sxs-lookup"><span data-stu-id="bfc26-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="bfc26-132">使用您要變更的參數和值來執行下列 Cmdlet (如需此 Cmdlet 之參數的詳細資訊，請參閱 Lync Server 管理命令介面檔) ：</span><span class="sxs-lookup"><span data-stu-id="bfc26-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bfc26-133">您可以建立特定站台的其他會議設定集。</span><span class="sxs-lookup"><span data-stu-id="bfc26-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="bfc26-134">請搭配使用 <STRONG>New- CsConferencingConfiguration</STRONG> Cmdlet 與站台身分識別。</span><span class="sxs-lookup"><span data-stu-id="bfc26-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="bfc26-135">當您建立站台的新會議設定時，站台設定的優先順序高於通用設定。</span><span class="sxs-lookup"><span data-stu-id="bfc26-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="bfc26-136">如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。</span><span class="sxs-lookup"><span data-stu-id="bfc26-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

