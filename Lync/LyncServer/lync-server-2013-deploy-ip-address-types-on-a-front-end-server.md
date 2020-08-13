---
title: Lync Server 2013：在前端伺服器上部署 IP 位址類型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e9c2f59cd3ee07e565a984ebb6f19d8ff07f50e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a>在 Lync Server 2013 的前端伺服器上部署 IP 位址類型

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-07-28_

使用拓撲產生器，執行下列程式中的步驟，以在前端伺服器上部署 IP 位址類型。

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>若要在前端伺服器上部署 IP 位址類型

1.  在 [ **Enterprise Edition 前端**集區] 底下的集區中，以滑鼠右鍵按一下伺服器，然後選取 [ **編輯屬性**]。  (或者，選取伺服器，然後按一下 [**動作**] 功能表中的 [**編輯屬性**]。 ) 

2.  在 **[編輯內容]** 對話方塊中，選取您想要設定的 IP 位址類型。針對雙重堆疊設定，選取 **[啟用 IPv4]** 和 **[啟用 IPv6]**，如下圖所示。
    
    **前端伺服器集區的 [編輯內容] 對話方塊**
    
    ![前端伺服器 [編輯內容] 對話方塊](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "前端伺服器 [編輯內容] 對話方塊")
    
      - **使用所有設定的 IP 位址**。如果您想要提供使用電腦上定義的任何 IP 位址，請選取此選項。
        
        <div>
        

        > [!NOTE]  
        > 此為 IP 版本 6 (IPv6) 組態的建議選項。

        
        </div>
    
      - **將服務使用方式限制為選取的 IP 位址**。 選取此選項指定在新伺服器上使用的特定位址。 如果您選取此選項，則必須輸入 **主要 IP 位址**的值。
    
      - **主要 IP 位址**。輸入伺服器將用於所有通訊 (公用交換電話網路 (PSTN) 除外) 的 IP 位址。輸入的 IP 位址必須符合選取位址類型的格式。
    
      - **PSTN IP 位址**。 安裝額外的網路介面卡 (NIC) s，以支援 Lync Server 2013 的 PSTN IP 位址設定，但不支援組合轉送伺服器角色。 如需 Lync Server 2013 支援的 NIC 設定的詳細資訊，請參閱 [伺服器硬體平臺的 Lync server 2013](lync-server-2013-server-hardware-platforms.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

