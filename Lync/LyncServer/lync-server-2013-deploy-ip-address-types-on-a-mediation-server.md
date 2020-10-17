---
title: Lync Server 2013：在轉送伺服器上部署 IP 位址類型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76dcde03d2a85eb45f7b2c28d6b7c7d99b41b20
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531480"
---
# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>在 Lync Server 2013 的轉送伺服器上部署 IP 位址類型

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-07-28_

使用拓撲產生器，執行下列程式中的步驟，以在轉送伺服器上部署 IP 位址類型。

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>在中繼伺服器上部署 IP 位址類型

  - 在 [拓撲產生器] 的 [中繼集區 **] 下，** 于集區中的伺服器上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。  (或者，選取伺服器，然後按一下 [**動作**] 功能表中的 [**編輯屬性**]。 ) 

  - 在 **[編輯內容]** 對話方塊中，選取您想要設定的 IP 位址類型。針對雙重堆疊設定，選取 **[啟用 IPv4]** 和 **[啟用 IPv6]**，如下圖所示。
    
    **中繼伺服器集區的編輯內容對話方塊**
    
    ![含 FQDN 的 Lync Server 一般屬性頁面](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "含 FQDN 的 Lync Server 一般屬性頁面")
    
      - **使用所有設定的 IP 位址**。如果您想要提供使用電腦上定義的任何 IP 位址，請選取此選項。
        
        <div>
        

        > [!NOTE]  
        > 此為 IP 版本 6 (IPv6) 組態的建議選項。

        
        </div>
    
      - **將服務使用方式限制為選取的 IP 位址**。選取此選項指定在新伺服器上使用的特定位址。如果您選取此選項，您必須輸入主要 IP 位址的值。
    
      - **主要 IP 位址**。輸入伺服器將用於所有通訊 (公用交換電話網路 (PSTN) 除外) 的 IP 位址。輸入的 IP 位址必須符合選取位址類型的格式。
    
      - **PSTN IP 位址**。 當轉送伺服器為獨立時，請定義 PSTN IP 位址。 此位址必須符合所選位址類型的格式。
        
        <div>
        

        > [!NOTE]  
        > 安裝額外的網路介面卡 (NIC) s，以支援 Lync Server 2013 的 PSTN IP 位址設定，但不支援組合轉送伺服器角色。 如需 Lync Server 2013 支援的 NIC 設定的詳細資訊，請參閱 <A href="lync-server-2013-server-hardware-platforms.md">伺服器硬體平臺的 Lync server 2013</A>。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

