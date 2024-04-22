import pandas as pd

def combine_participants(input_files):
  """
  Combines participant lists from multiple files into a single spreadsheet.

  Args:
      input_files (list): List of file paths containing participant data.

  Returns:
      pd.DataFrame: Combined participant data with columns for Name, Team, Type, Phone, and Email.
  """
  all_participants = []
  for file in input_files:
    # Read data from each file (assuming specific format)
    data = pd.read_csv(file)

    # Handle missing columns (replace with None)
    for col in ['Participant Name', 'Team Name', 'Participant Type', 'Participant Phone Number', 'Participant Email']:
      '''if col not in data.columns:
        data[col] = None'''

    all_participants.append(data)

  # Combine dataframes from all files
  combined_df = pd.concat(all_participants, ignore_index=True)

  # Fill missing values with 'NA'
  '''
  combined_df.fillna('NA', inplace=True)
'''
  return combined_df

# Example usage (replace 'participant_list*.csv' with your actual file paths)
participant_data = combine_participants(['anon_data2.xlsx - Sheet1.csv', 'anon_data1.xlsx - Sheet1.csv'])

# Save the combined data to a new spreadsheet
participant_data.to_excel('combined_participants.xlsx', index=False)

participant_data.to_csv('combined_participants.csv', index=False)

print("Participant data combined successfully!")
