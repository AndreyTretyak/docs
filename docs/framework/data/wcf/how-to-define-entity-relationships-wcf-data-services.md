---
title: "How to: Define Entity Relationships (WCF Data Services)"
ms.date: "03/30/2017"
dev_langs: 
  - "csharp"
  - "vb"
helpviewer_keywords: 
  - "WCF Data Services, changing data"
ms.assetid: cc255524-1534-4fae-b83c-250933d5a72b
---
# How to: Define Entity Relationships (WCF Data Services)
When you add a new entity in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], any relationships between the new entity and related entities are not automatically defined. You can create and change relationships between entity instances and have the client library reflect those changes in the data service. For more information, see [Updating the Data Service](updating-the-data-service-wcf-data-services.md).  
  
 The example in this topic uses the Northwind sample data service and autogenerated client data service classes. This service and the client data classes are created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).  
  
## Example  
 The following example creates a new object instance and then calls the <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> method on the <xref:System.Data.Services.Client.DataServiceContext> to create the item in the context along with the link to the related order. An HTTP POST message is sent to the data service when the <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> method is called.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addorderdetailtoorderauto)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addorderdetailtoorderauto)]  
  
## Example  
 The following example shows how to use the <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> method to add an `Order_Details` object to a related `Orders` object with a reference to a specific `Products` object. The <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> and <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> methods define the relationships. In this example, the navigation properties on the `Order_Details` object are also explicitly set.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addorderdetailtoorder)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addorderdetailtoorder)]  
  
## See also

- [WCF Data Services Client Library](wcf-data-services-client-library.md)
- [How to: Add, Modify, and Delete Entities](how-to-add-modify-and-delete-entities-wcf-data-services.md)
