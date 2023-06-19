## Number of Shipments Per Month 
import pandas as pd  
amazon_shipment.drop('weight', axis=1, inplace=True)  
amazon_shipment['shipment_id_combo'] = amazon_shipment['shipment_id']+amazon_shipment['sub_id']  
amazon_shipment['formatted_date'] = amazon_shipment['shipment_date'].dt.year.astype(str) +"-0"+ amazon_shipment['shipment_date'].dt.month.astype(str)  
amazon_shipment.drop(['shipment_id', 'sub_id', 'shipment_date'], axis=1, inplace=True)  
amazon_shipment.groupby('formatted_date').count().reset_index()
