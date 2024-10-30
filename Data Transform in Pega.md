# Data Transform in Pega

Data Transform is a feature in Pega that allows you to manipulate and process data within a case or across cases. It’s used to transform data from one structure to another, perform conditional processing, and set default values in Pega applications.

## Key Components and Properties

### 1. **Mapping Data**
   - **Role**: Mapping data is crucial in setting up relationships between source and target properties.
   - **Scope**: Source data can be from any page (data page, clipboard page) and can include **data from an external system**.
   - **Default Values**: You can define default values, especially for new records or fields that require initialization.

### 2. **Actions**
   Actions define what transformations are applied to the data. Common actions include:

   - **Set**: Used to assign a value to a property.
   - **Remove**: Deletes a property or a page from the clipboard.
   - **Append and Map to**: Maps data to a list structure.
   - **Call Data Transform**: Calls another Data Transform for nested processing.

### 3. **Target Property**
   - Defines the destination property where the data will be stored after transformation.

### 4. **Relation**
   - Defines the relationship between source and target properties, such as direct mapping, conditional mapping, or computed mapping.

### 5. **Expression**
   - Allows setting up conditional expressions for data transformation based on specific criteria.
   - Expressions can use Pega's inbuilt functions to perform operations like arithmetic, concatenation, and logical comparisons.

### 6. **Page and Property References**
   - **Page**: Refers to the specific data page or clipboard page that holds the data.
   - **Property**: Refers to individual fields or variables on the page.

### 7. **Parameters**
   - Parameters allow you to pass data into the Data Transform, making it reusable with different inputs.
   - Example: You might pass a customer ID as a parameter to retrieve specific customer data.


## Key Scenarios for Using Data Transforms

### 1. **Initialization**
   - Set default values for properties when a new case or data page is created.
   - Example: Setting default values for `OrderStatus` or `CustomerType`.

### 2. **Data Mapping Between Cases**
   - Map data between cases, such as copying customer details from one case to another.
   - Example: Mapping `Customer ID`, `Name`, and `Address` from an order case to a fulfillment case.

### 3. **Data Manipulation**
   - Modify data based on conditional logic or calculations.
   - Example: Calculating total price based on quantity and unit price, or applying discounts.

### 4. **Integration and Service Data Handling**
   - When retrieving data from external systems, Data Transform can help structure the data to fit within the Pega model.
   - Example: Mapping data from an external REST service into the Pega property structure.

## Summary Table

| Rule Type          | How to Call a Data Transform                                |
|--------------------|-------------------------------------------------------------|
| **Activity**       | Use `Apply-DataTransform` method.                           |
| **When Rule**      | Indirectly call via an Activity (not recommended).          |
| **Data Transform** | Use **Call Data Transform** action within another Data Transform. |
| **Flow Action**    | Set as **Pre-Processing** or **Post-Processing** option.    |
| **Section**        | Use Event Action to run an Activity that calls the Data Transform. |


## Best Practices for Data Transform in Pega

1. **Modularity**: Use reusable Data Transforms for common data manipulations across cases.
2. **Parameterization**: Make use of parameters for flexibility and reusability.
3. **Clarity**: Name Data Transforms and properties clearly to improve readability.
4. **Avoid Hard-Coding**: Use expressions and parameters instead of hard-coded values where possible.

---

By following these principles, you can make effective use of Data Transforms in Pega to streamline data handling, ensure data consistency, and improve application performance.
